---
date: 2024-06-27T20:18
tags:
  - linting
  - CICD
---
One of the most popular way to do precommit is to use [Husky](https://github.com/automation-co/husky) 
Here is an example hot to use Husky and Gonangci-lint for linting on pre-commit

```shell
> go install github.com/automation-co/husky@latest
#add the hook to execute command on commit
> husky init .
> husky add pre-commit "golangci-lint run"
#before that it may be neccesary to perform formating with "go fmt"
> husky add pre-commit "go fmt ./..."
```