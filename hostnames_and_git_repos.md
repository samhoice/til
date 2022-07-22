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

To have a second github account, you can set another hostname (I used github.com) and the second account info. Like this:
```
Host github.com
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_ecdsa_2
```
Now the default connection to github will use the second identity file, and if you clone `github_me` it will use the other identity file. I also have those repos configured to use a different github user, but that's in the git configuration.

We also need to specify:
```
Host *
  IdentitiesOnly yes
```
So that it won't just try the keys in order. If a key is successful but doesn't have access, the connection will give up. So we need to only use the specified identities. (I might need to rewrite this later)
