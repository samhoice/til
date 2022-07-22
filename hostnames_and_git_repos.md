# SSH Hostnames and Git Repos

Trying to set up ssh connections to various different repos. I have two identities and two github accounts. I want to be able to set up the repo to use the right identity file, but they are both pointing to github.com.

A normal config stanza might look like

```
Host github.com
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_ecdsa
```

This will let you connect to github using the user `git` and the specified identity.

What you can do instead is:
```
Host github_me
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_ecdsa
```

And now you can connect to github_me and ssh will sort it out.
`git clone git@github_me:samhoice/til.git`

