# Django - Testing reference

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
