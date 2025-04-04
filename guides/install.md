---
description: Installing ray server (rays)
icon: arrow-down-to-line
---

# Installation

{% hint style="warning" %}
This page is a work in progress, since the rays installation procedure is not finished
{% endhint %}

This guide will walk you through how to install ray server onto a Linux or Windows machine.

## 1. Getting an installation package

If you want the latest stable release (recommended), navigate to [the releases page](https://github.com/pyrretsoftware/ray/releases) and find the release asset that matches your OS and processor architecture. If you want the latest unstable build, see the [Github actions page](https://github.com/pyrretsoftware/ray/actions).

Some of the architecture names can be a bit confusing, so see the list below if you need help picking the right installation package.

* **386** refers to the 32 bit version of the x86 architecture, found in older processors made by Intel. The name comes from the Intel 80386; the first 32 bit x86 processor.
* **amd64** refers to the 64 bit version of the x86 architecture  (x86-64), found in most processors made by AMD and Intel. It's the most common architecture for PC's and servers.

The rest of the architecture names are pretty self explanatory.&#x20;

## 2. Picking your installation directory

After downloading your installation package, it's time to choose where you want ray server to be installed. It's recommended to use a directory like `/usr/bin` on Linux (see below) or `%LOCALAPPDATA%` on Windows.

Now unzip your installation package and move the `rays` or `rays.exe` file into the directory you picked.

## 3. Running the setup wizard

Finally, run `sudo ./rays setup` on Linux or `rays setup` on Windows to begin the installation.

## 4. Finishing up

See the steps below depending on your platform

{% tabs %}
{% tab title="Linux" %}
If you didn't pick a directory that's included in the path variable by default like `/usr/bin` , you'l need to [add your installation directory to your path](https://askubuntu.com/a/60221) in order to use the `rays` command globally.

If your Linux distro uses systemd, ray server will automatically be registered as a service and enabled. If you have another service/daemon manager, you'l have to register rays as a service/daemon manually. See the commands below for what to specify when doing that:

* Starting: `sudo rays --daemon`&#x20;
* Stopping: `sudo rays stop`&#x20;
* Reloading: `sudo rays reload`&#x20;
{% endtab %}

{% tab title="Windows" %}
In order to use the `rays` command globally, you'l need to [add the installation directory you picked previously to your path variable.](https://www.architectryan.com/2018/03/17/add-to-the-path-on-windows-10/)

Currently, ray server does not register itself as a Windows service automatically. You can try to do that manually, or you can add a batch script that launches rays to your autostart directory (shell:startup). For example:

{% code title="shell:startup\rays.bat" %}
```batch
rays --daemon
```
{% endcode %}
{% endtab %}
{% endtabs %}





