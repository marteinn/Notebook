# Tip - Adding public identity to authorized_keys

## Manually

Make sure authorized_keys exist with correct permissions

```
mkdir ~/.ssh
touch ~/.ssh/authorized_keys
chmod 700 ~/.ssh
chmod 600 ~/.ssh/authorized_keys
```

Then append your key to `authorized_keys`

## Autmatically

This will automatically append your key to authorized_keys.

`ssh-copy-id user@example.com`
