# Syncing container time on Mac OS

WHen you place your computer in hibernation the local container time starts to drift

Run this to fix it:

```
docker run --rm --privileged alpine hwclock -s
```
