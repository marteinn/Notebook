# Tip - Using a s3 bucket name with a dot with django-storages (boto)

Put this in your settings.

```python
from boto.s3.connection import OrdinaryCallingFormat, S3Connection
S3Connection.DefaultHost = 's3-eu-west-1.amazonaws.com'  # Depending on region

AWS_S3_CALLING_FORMAT = OrdinaryCallingFormat()
```
