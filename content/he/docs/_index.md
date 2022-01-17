---
title: פרויקט Falco
description: אבטחת זמן-ריצה לטכנולוגיות קלאוד-נייטיב
menu:
  main:
    name: דוקומנטציה
    linkTitle: דוקומנטציה
    weight: 40
---

## מה זה Falco?

פרויקט
Falco
הוא כלי זמן-ריצה בעל קוד פתוח שנבנה במקור על ידי [Sysdig, Inc](https://sysdig.com).

Falco
[
נתרם ל-CNCF
והוא עכשיו פרויקט הדגרה של CNCF
](https://www.cncf.io/blog/2020/01/08/toc-votes-to-move-falco-into-cncf-incubator/).

## מה Falco עושה?

Falco 
מתעל קריאות מערכת על מנת לאבטח ולנטר מערכת, ע"י:
- ניתוח קריאות מערכת של לינוקס מהקרנל בזמן-ריצה.
- וידוא ערוץ המידע מול מנוע חוקים עוצמתי.
- התרעה כאשר חוק מופר.

 למידע נוסף, קרא על 
 [חוקי Falco](rules).

## מה Falco מאבחן?

Falco מגיע עם סט של חוקים דיפולטיביים שבוחנים את הקרנל ומזהים התנהגות חריגה כדוגמת:

 - Privilege escalation using privileged containers
 - Namespace changes using tools like `setns`
 - Read/Writes to well-known directories such as `/etc`, `/usr/bin`, `/usr/sbin`, etc
 - Creating symlinks
 - Ownership and Mode changes
 - Unexpected network connections or socket mutations
 - Spawned processes using `execve`
 - Executing shell binaries such as `sh`, `bash`, `csh`, `zsh`, etc
 - Executing SSH binaries such as `ssh`, `scp`, `sftp`, etc
 - Mutating Linux `coreutils` executables
 - Mutating login binaries
 - Mutating `shadowutil` or `passwd` executables such as `shadowconfig`, `pwck`, `chpasswd`, `getpasswd`, `change`, `useradd`, `etc`, and others.


## What are Falco rules?

Rules are the items that Falco asserts against. They are defined in the Falco configuration file, and represent the events you can check on the system. For more information about writing, managing, and deploying rules, see Falco [Rules](rules).

## What are Falco alerts?

Alerts are configurable downstream actions that can be as simple as logging to `STDOUT` or as complex as delivering a gRPC call to a client. For more information about configuring, understanding, and developing alerts, see [Falco Alerts](alerts). Falco can send alerts to :

- Standard Output
- A file
- Syslog
- A spawned program
- A HTTP[s] end point
- A client through the gRPC API


## What are the Components of Falco?

Falco is composed of three main components:

 - Userspace program - is the CLI tool `falco` that you can use to interact with Falco. The userspace program handles signals, parses information from a Falco driver, and sends alerts.

 - Configuration - defines how Falco is run, what rules to assert, and how to perform alerts. For more information, see [Configuration](configuration).

 - Driver - is a software that adheres to the Falco driver specification and sends a stream of system call information. You cannot run Falco without installing a driver.
Currently, Falco supports the following drivers:

    - (Default) Kernel module built on `libscap` and `libsinsp` C++ libraries
    - BPF probe built from the same modules
    - Userspace instrumentation

    For more information, see [Falco Drivers](/docs/event-sources/drivers/).



