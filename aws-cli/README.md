# aws cli - Cheat sheet

## Configure

```
export AWS_ACCESS_KEY_ID=XXXXXXXXXXXXXXXXXXXX
export AWS_SECRET_ACCESS_KEY=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
```


## S3

### Show buckets
`aws s3 ls`

### Show files in bucket
`aws s3 ls s3://<BUCKET_NAME>`

### Sync files to bucket
`aws s3 sync my/catalog s3://<BUCKET_NAME>/path`

### Sync files to bucket with read access
`aws s3 sync my/catalog s3://<BUCKET_NAME>/path --acl public-read`

### Remove file from bucket
`aws s3 rm s3://<BUCKET_NAME>/path/subdir/<FILENAME>`
