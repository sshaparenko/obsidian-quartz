---
date: 2024-04-10T16:00
tags:
  - Docker
cssclasses:
  - pen-white
---
**[From this article](https://depot.dev/blog/docker-clear-cache)**

```
#to see how much spase is used by docker
> docker system df
```

```
#to remove build cache
> docker buildx prune -f
```
