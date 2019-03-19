# Django - Testing reference

- Testing management command
- Overriding auto_now_add, auto_now field values
- Passing a proper json payload through client.post
- Testing email
- Testing update on authenticated django rest framework endpoint
- Sending a file through a DRF endpoint


## Testing management command

```python
from django.core.management import call_command
from django.test import TestCase
from django.utils.six import StringIO

class ClosepollTest(TestCase):
    def test_command_output(self):
        out = StringIO()
        call_command('closepoll', stdout=out)
        self.assertIn('Expected output', out.getvalue())
```

- [Reference](https://docs.djangoproject.com/en/1.9/topics/testing/tools/#management-commands)


## Overriding auto_now_add, auto_now field values

```python
from datetime import timedelta
import mock  # pip install mock

from django.utils import timezone
from django.utils.dateparse import parse_datetime
from django.test import TestCase

from example.factories import PostFactory


class AnonymizeOrderaTest(TestCase):
    def test_anonymize_orders_command_exists(self):
        A_KNOWN_TIME = parse_datetime('2000-01-01 12:00:00Z')

        with mock.patch('django.db.models.fields.timezone.now') as mock_now:
            mock_now.return_value = A_KNOWN_TIME

            post = PostFactory.create(slug='about')
```

- [Reference](https://devblog.kogan.com/blog/testing-auto-now-datetime-fields-in-django)


## Passing a proper json payload through client.post

```python
resp = self.client.post(
    reverse("exampleapp:my_route"),
    json.dumps({"first_name": "Martin", "last_name": "Sandström"}),
    content_type="application/json",
)
```


## Testing email

```python
from django.test import TestCase
from django.core import mail


class TestFeedbackApi(TestCase):
    def test_feedback_gets_sent(self):
        self.assertEqual(len(mail.outbox), 0)

        # Some action that triggers email sent

        self.assertEquals(len(mail.outbox), 1)

        self.assertEqual(mail.outbox[0].subject, "Mail subject")
        self.assertEqual(mail.outbox[0].from_email, "no-reply@email.com")
```


## Testing update on authenticated django rest framework endpoint

```python
import json

from django.test import TestCase
from django.urls import reverse
from rest_framework.test import APIClient

from myapp.factories import UserFactory


class TestUpdateUserProfileApiView(TestCase):
    def setUp(self):
        self.client = APIClient()

        self.user = UserFactory(username="test", email="test@test.com")

    def test_non_auth_user(self):
        url = reverse("myapp:api_update_user")
        response = self.client.put(
            url,
            json.dumps({"email": "random@hello.com"}),
            content_type="application/json",
        )

        self.assertEqual(response.status_code, 403)

    def test_update_auth_user(self):
        self.client.force_authenticate(user=self.user)

        url = reverse("myapp:api_update_user")
        response = self.client.put(url, {
            "first_name": "Random",
        })
        self.user.refresh_from_db()

        self.assertEqual(response.status_code, 200)
        self.assertEqual(self.user.first_name, "Random")
```

## Sending a file through a DRF endpoint

```python
import tempfile
from PIL import Image

from django.test import TestCase
from rest_framework.test import APIClient

class TestUpdateUserProfileApiView(TestCase):
    def setUp(self):
        self.client = APIClient()

    def test_non_auth_user(self):
        image = Image.new('RGB', (100, 100))
        tmp_file = tempfile.NamedTemporaryFile(suffix='.jpg')
        image.save(tmp_file)

        url = "/my_endpoint/"
        with open(tmp_file.name, 'rb') as image_data:
            response = self.client.post(
                url, {"image": image_data}, format='multipart'
            )

        self.assertEqual(response.status_code, 201)
```
