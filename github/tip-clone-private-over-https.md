# Tip - How to clone provate repositories over https

- Head to your [Personal access tokens](https://github.com/settings/tokens)
- Create [new token](https://github.com/settings/tokens/new)
- Name can be whatever, just make sure you check the `repro` permission
- Copy the generated token (it won´t appear again!)
- Now when you clone, prepend the key before github.com
    `git clone https://<token>@github.com/user/repro.git`
