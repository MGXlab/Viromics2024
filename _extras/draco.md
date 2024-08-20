---
layout: page
title: Access to Draco
permalink: /draco/index.html
---

[Draco](https://wiki.uni-jena.de/pages/viewpage.action?pageId=22453002) is a high-performance cluster created and maintained by the Universitätsrechenzentrum. It is [available for members of Thuringian Universities](http://sternb.gitpages.tpi.uni-jena.de/draco-101-2023-01/#5).  

## SLURM ARCHITECTURE

This is a simplified overview of the slurm architecture. 

![slurm_architecture_simple](https://github.com/user-attachments/assets/f6baeec5-ddf0-413d-909c-aa2d2b947bd5)


To log in, you can use [ssh](http://sternb.gitpages.tpi.uni-jena.de/draco-101-2023-01/#15): 

```bash
# replace <fsuid> with your actual id like ab12cde

ssh <fsuid>@login1.draco.uni-jena.de
```

## Getting into Draco

### Terminal or ssh client  
You will require a terminal or an ssh client to access Draco, which is a remote server. 

#### Linux and MacOS
Lucky! You already have a terminal integrated into the OS. You can use this or can also use VSCode (see below).

#### Windows
Please switch to either a Linux or MacOS...

Just joking! You can either install the Windows Subystem for Linux (WSL) or **VScode (recommended)**

[Instructions for WSL](https://learn.microsoft.com/en-us/windows/wsl/install)

[Instructions for installing Visual Studio Code](https://code.visualstudio.com/docs/setup/windows)

#### Adding a ssh remote server to VSCode

![image](https://github.com/user-attachments/assets/3db3b016-b33f-469f-ac3f-df490d1f34b8)

![image](https://github.com/user-attachments/assets/d8e9d52b-6695-4608-a33f-9e4a28d11a04)

Then put in your password and you are in!
