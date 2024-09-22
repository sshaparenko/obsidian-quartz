---
date: 2024-06-08T16:34
tags:
  - ssh
  - cryptography
---
## How to generate SSH public and private key

In order to generate SSH we will use new command
```
ssh-keygen -t rsa -f rsa -m PEM
```

`-t rsa` -> specifies the type of cryptographic algorithm to use (see [[202406081646 RSA|RSA]])
`-m PEM` -> specifies the format of the key file. **By default it’s OpenSSH.**(see [[202406081645 PEM|PEM]])

