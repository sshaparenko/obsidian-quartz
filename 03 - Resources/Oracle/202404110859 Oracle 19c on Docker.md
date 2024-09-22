---
date: 2024-04-11T08:59
tags: []
cssclasses:
---
2**Download Oracle19c [here](https://www.oracle.com/database/technologies/oracle-database-software-downloads.html)**

>[!tip] Go into admin mode
>
>```
> sudo -i
> ```

```
#create docker dir in var
> user:var/ mkdir docker
> user:var/ cd docker
> user:var/docker/ 
```

```
#in docker dir clone the repo
> git clone https://github.com/oracle/docker-images.git
```

```
#move into /19.03.0
> cd ~/docker-images/OracleDatabase/SingleInstance/19.3.0
```

```
#in Dockerfile file change the next param
ARG SLIMMING = false
```

```
#in ~/SingleInstance do
> ./buildContainerImage.sh -v 19.3.0 -e
```

```
#run image by
> docker run --name "oracle19.3" -p 1521:1521 -p 5500:5500 -e ORACLE_PDB=orapdb1 -e ORACLE_PWD=topsecretpass -e ORACLE_MEM=3000 -v /opt/oracle/oradata -d oracle/database:19.3.0-ee
```

```
> docker exec -it oracle19.3 /bin/bash
> ps -ef | grep pmon
> sqlplus / as sysdba
```

```
> docker exec -it oracle19.3_postservice /bin/bash
> ps -ef | grep pmon
> sqlplus / as sysdba
```
