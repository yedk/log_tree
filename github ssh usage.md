[TOC]

# generate SSH key

1.ssh-keygen -t rsa -C 'email'

# Add public key in github repository

# Make sure you have a key that is being used

# Verify the public key is attached to your count

2.ssh-agent -s 
3.ssh-add privatekey file

# verify your connection to github

```bash
    4.ssh -T git@github.com
```
