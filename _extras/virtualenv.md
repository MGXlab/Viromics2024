---
layout: page
title: Setting up a virtual environment for python
permalink: /sbatch/index.html
---

## Overview

Throughout the course, we will use python to analyze our data and visualize the results. 
Python can be run from a [virtual environment](https://docs.python.org/3/library/venv.html),
which is a directory containing a python executable, python packages and script to activate
and deactivate the environment within a bash session. Activating the environment will tell
your terminal session to use the python binary and packages located within it. This is a
convenient way to define a fixed set of dependencies and their version for your code to be
run on other systems, which might have a different version of python installed.

## Set up the virtual environment

You will use such an environment on draco. To set it up, you can use the following script:

```bash
# Use python3.9 on draco to create a virtual environment
$ python3.9 -m venv path/to/your/py3env

# activate the environment
$ source path/to/your/py3env/bin/activate

# update pip
$ pip install --upgrade pip
```
{: .language-bash}

## Add packages to an existing virtual environment
To add a package to an existing environment, you activate it again and use pip to install it:

```bash
# activate the environment
$ source path/to/your/py3env/bin/activate

# install package
$ pip install your_package

# install multiple packages
$ pip install package1 package2
```
{: .language-bash}
