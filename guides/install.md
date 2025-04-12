---
description: Installing ray server (rays)
icon: arrow-down-to-line
---

# Installation

This guide will walk you through how to install ray server onto a Linux or Windows machine.

## 1. Getting an installation package

If you want the latest stable release (recommended), navigate to [the releases page](https://github.com/pyrretsoftware/ray/releases) and find the release asset that matches your OS and processor architecture. If you want the latest unstable build, see the [Github actions page](https://github.com/pyrretsoftware/ray/actions).

Some of the architecture names can be a bit confusing, so see the list below if you need help picking the right installation package.

* **386** refers to the 32 bit version of the x86 architecture, found in older processors made by Intel. The name comes from the Intel 80386; the first 32 bit x86 processor.
* **amd64** refers to the 64 bit version of the x86 architecture  (x86-64), found in most processors made by AMD and Intel. It's the most common architecture for PC's and servers.

The rest of the architecture names are pretty self explanatory.&#x20;

## 2. Unzip the archive

Now, unzip the zip archive you just downloaded. You will be left with an installation package (the build.rpack) file, as well as the rayinstall utility to help you install it.

## 3. Running the setup wizard

Finally, run `sudo ./rayinstall i build.rpack` on Linux or `rayinstall i build.rpack` as an admin on Windows to begin the installation.

## 4. Finishing up

{% hint style="success" %}
If your server uses Linux with systemd (eg. Fedora, Red Hat, Debian, Ubuntu, OpenSUSE or Arch) you do not need to do anything.
{% endhint %}

See the steps below depending on your platform.

{% tabs %}
{% tab title="Linux" %}
If your Linux distro doesn't use systemd, you'l have to register rays as a service/daemon manually if you want it to be automatically started. See the commands below for what to specify when doing that:

* Starting: `sudo rays --daemon`&#x20;
* Stopping: `sudo rays stop`&#x20;
* Reloading: `sudo rays reload`&#x20;
{% endtab %}

{% tab title="Windows" %}
In order to use the `rays` command globally, you'l need to [add the %USERPROFILE% directory to your path variable.](https://www.architectryan.com/2018/03/17/add-to-the-path-on-windows-10/)

Currently, ray server does not register itself as a Windows service automatically. You can try to do that manually, or you can add a batch script that launches rays to your autostart directory (shell:startup). For example:

{% code title="shell:startup\rays.bat" %}
```batch
rays --daemon
```
{% endcode %}
{% endtab %}
{% endtabs %}





