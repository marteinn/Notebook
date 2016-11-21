# Tip - Dynamic prompt answers in Fabric

I couldn't find much examples on how you supply [prompt](http://docs.fabfile.org/en/1.10/usage/env.html#prompts) values in Fabric, so here's a small rundown.

Lets start with a simple example. Import settings, supply prompts and the value you would like to supply, then wrap + run.


```python
from fabric.context_managers import settings

prompts = {
    "Your prompt: ": "yes"
}

with(settings(prompts=prompts)):
    run("servercommand")
```


A real world example for matching a ssh passhrase[1] would look like this:

```python
prompts = {
    "Enter passphrase for key '/root/.ssh/id_rsa': ": "my passphrase"
}
```


A trick is that fabric uses endswith to validate phrase, so passing ": " will match the same passprhase as the above example.

```python
prompts = {
    ": ": "my passphrase"
}
```

[1]. Please don't use this in production, either use env.password or env.forward_agent=True.
