---
date: 2024-04-16T16:08
tags:
  - Docker
  - Intellij
---
**If Intillij IDEA was installed with flatpak => this command will help to solve `#Cannot connect to the Docker daemon at unix:///var/run/docker.sock.`**

```
> flatpak list #to get list of apps and appIDs

> flatpak override --user --filesystem=/run/docker.sock com.jetbrains.Intellij-IDEA-<ULIMATE or COMMUNITY>
```

