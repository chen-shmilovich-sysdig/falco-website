---
title: איך מתחילים?
description: איך מתחילים עם Falco?
weight: 2
---
תוכלו להתקין את
Falco
על שרת מקומי, בענן, ב-cluster
קוברנטיס מנוהל, או ב-cluster
קוברנטיס כמו
K3s
שרץ
על מכשירי 
IOT
ומחשוב קצה.

## Falco Architecture

Falco can detect and alert on any behavior that involves making Linux system calls. Falco alerts are triggered based on specific system calls, arguments, and properties of the calling process.  Falco operates at the user space and kernel space. The system calls are interpreted by the Falco kernel module. The syscalls are then analyzed using the libraries in the userspace. The events are then filtered using a rules engine where the Falco rules are configured. Suspicious events are then alerted to outputs that are configured as Syslog, files, Standard Output, and others.


![Falco Architecture](/docs/images/falco_architecture.png)
## Deployment
Currently, you can deploy Falco by:
- [Downloading](/docs/getting-started/download) and running Falco on a Linux host or running Falco userspace program in a container, with a driver installed on the underlying host.
- [Building](/docs/getting-started/source) from source and then running Falco on a Linux host or on a container.

