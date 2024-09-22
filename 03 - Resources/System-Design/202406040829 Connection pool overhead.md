---
date: 2024-06-04T08:29
tags:
  - Architecture
  - System-Design
cssclasses:
  - embed-white
---
![[Pasted image 20240604082956.png]]

The connection creation overhead occurs when with each new request to the system, a new connection is created between Web App, Service App and DB

In order to solve this overhead - a **connection pool** should be utilized<u> for Web and Service App.</u> Connection pool **allows to reuse** already created connections.

