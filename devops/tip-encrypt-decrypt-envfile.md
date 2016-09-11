# Tip - Encrypt/Decrypt envfile

- Encrypt

```
openssl aes-256-cbc -e -in .env -out .env-encrypted -k key
```

- Decrypt

```
openssl aes-256-cbc -d -in .env-encrypted -out .env -k key
```
