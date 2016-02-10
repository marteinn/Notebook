# Errors

## Error: Failed to register layer

Issue: `ERROR: failed to register layer: Untar error on re-exec cmd: fork/exec /proc/self/exe: cannot allocate memory`

Got this error while trying to pull down the nginx image from docker on a vagrant box. Solved it by raising memory to 512.
