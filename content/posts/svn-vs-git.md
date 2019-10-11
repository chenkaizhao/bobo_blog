---
title: Use SVN or GIT for version control
date: 2018-08-26T18:56:28-05:00
draft: false
categories: 
- website construction
tags: 
- svn
- git
- version control
description: "A quick read on how to choose to use SVN or GIT for version control"
cover: /img/cover/default5.jpg
#license: "BY-NC-SA"
---

# **What is version control and why use it**
Version control is a software engineering technique that ensures that the same files edited by one or different people are updated during the development process. Version Control Systems(VCS) are a category of software tools that record one or several file content changes for future review of a particular version.

# **VCS**
## 1. Local version control system(*LVCS*)
Many LVCS have been developed for a long time, and most of them use a simple database to record the difference in update of files.

![](/static/img/posts/localvcs.png)

One of the most popular is called RCS, which is still visible on many computer systems so far. It works by saving the patch set on the hard disk, by applying all the patchs, we can recalculate the file contents of each version.

## 2. Centralized version control system(*CVCS*)
So, how do we get developers working on different systems to work together?
CVCS came into being. Such as [CVS](https://en.wikipedia.org/wiki/Concurrent_Versions_System), [Subversion](http://subversion.apache.org/) and Perforce etc., have a single, centrally managed server that keeps revisions of all files, and people who work together connect to the server through the client, fetching the latest files or submitting them. This has become the standard practice for VCS.

![](/static/img/posts/cvcs.png)

Advantages: Everyone can see what other people are doing to certain extent, administrators can also easily control the permissions of each feveloper. Managing a CVCS is much easier than maintaining a local database on each client.
Disadvantages: If the central server goes down, then we cant work together and submit any update. If the disk on which the central database resides is corrupted and doesnt have a proper backup, theres no doubt you will lose all data(including the entire change history of the project) but leaving a snapshot that is kept on the respective machine.
### *<font color = orange>Subversion</font>*([SVN](http://subversion.apache.org/))
SVN is short for Subversion. Its an open-source CVCS. Compared to RCS and CVS, it uses a branch management system, which is designd to replace CVS.
As an open source VCS, Subversion manages data that changes over time. These are saved in a central <font color = green>repository</font>. This repository is much like a normal file server, but it remembers every file change. This way you can restore the file to the old version or browse the history. Subversion is a general-purpose system that can be used to manage any type of file, including source code.

Advantages:
1. Convenient management, clear logic, simple operation, quick to get started
2. Centrlized server can ensure security
3. Good code consistency
4. Good directory-level permission control system

Disadvantages:
1. High performance requirements on the server, database capacity often increases
2. Must be networked
3. Not suitable for open source development
4. Not flexible for branch management

## 3. Distributed version control system(*DVCS*)
In such systems, like [GIT](https://git-scm.com/), [Mercurial](https://www.mercurial-scm.org/), [Bazaar](https://bazaar.canonical.com/en/), and [Darcs](http://darcs.net/), the client does not only extract the latest version of file, but completely mirrors the code repository. In this way, any server has failed, and can be recovered with any mirrored local repository. **Because every cloning operation is actually a complete backup of the repository.**

![](/static/img/posts/dvcs.png)

Such systems can be specified to interact with several different remote code repositories. Therefore, you can collaborate with people in different groups in a project. Like you can set up different collaborattion processes as needed, such as hierarchical model workflows, which were not possible in previous centralized systems.

### *<font color = orange>GIT</font>*([SVN](https://git-scm.com/))
Git is an open source DVCS, for efficient, high-speed processing of project management from small to large.
Git is VC software developed by Linus Torvalds to help manage Linux kernel development.
The biggest difference between DVCS and CVCS is that developers can submit the code or project to the local, each developer copies a complete Git repository on the local machine by cloning.
