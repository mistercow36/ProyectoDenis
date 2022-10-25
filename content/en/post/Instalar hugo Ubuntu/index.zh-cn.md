---
title: Installing hugo on Ubuntu
description: Installation of hugo for Ubuntu
date: 2022-10-17
slug: Instalacion-hugo-ubuntu
image: "helena-hertz-wWZzXlDpMog-unsplash.jpg"
categories:
    - Installation
    - Hugo
    - Ubuntu
---

## How to install hugo

**Install Snap**

To install Hugo on Linux we are going to use the Snap package manager. For this reason, the first thing we are going to do is check if we have this manager installed, for this we will use the following command:

>``
    snap version
``

If the result is similar to the following, it means that it is installed

![Snap version installed](version.jpg)


If something similar does not appear, it means that it is not installed, to do so simply add the following in the command console

>``
apt-get install snapd -y
``

And we would return to the previous step to check if it is installed

## Install Hugo-Extended

Now we will use the **Snap** manager to install Hugo-Extended, to do so you have to access a command console and enter the following:

>``
snap install hugo --channel=extended
``

![Logo Ubuntu](helena-hertz-wWZzXlDpMog-unsplash.jpg)

