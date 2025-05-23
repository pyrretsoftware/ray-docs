---
description: Installing and using rray (remote ray)
icon: chart-network
---

# Using rray

Rray is a tool used to easily communicate with remote ray server. It's designed to run on development machines and builds are available for almost all platforms.&#x20;

### Installation

Rray can easily be downloaded through through pyrret's package server. You can navigate to [pkgs.pyrret.com](https://pkgs.pyrret.com/) and find a binary by choosing os and architecture. You usually want rray installed in `/usr/bin` on Linux or Macos and `%%USERPROFILE%%` on Windows. See the commands below depending on platform.

On Linux/Macos, if you have wget installed:

```bash
cd /usr/bin && wget "https://pkgs.pyrret.com/linux/ARCH/rays"
```

Making sure to replace ARCH with your actual processor architecture (386, amd64, arm64)

On Windows, using powershell:

```batch
cd %%USERPROFILE%% && wget "https://pkgs.pyrret.com/windows/amd64/rays"
```

Making sure to replace amd64 if you're running 32 bit Windows or Windows for arm (with 386 or arm64)

{% hint style="info" %}
On Windows, make sure to add %%USERPROFILE%% to your path variable, that way you can use rray everywhere.
{% endhint %}

If your platform isn't on our package server, you can also build rray yourself. It compiles to any operating systems and architectures supported by golang, so just clone the ray repository and run `go build` in the rray directory. A binary named `rray` or `rray.exe` will be produced.

### Adding a remote

First up, you'll need to make sure the remote you're connecting to has an active ssh running that accepts connection and you need to have authentication for that server. If you are authenticating via public key, rray will use the ssh key already stored on your system. If you use a password, you'll have to enter the password when adding the remote and ray will automatically use that.

Type `rray remote add`  and fill in the fields until you're done, giving the remote a name, hostname (domain or ip), as well as adding one or more authentication methods.

### Using the remote

To use the remote, specify it's name as the `r` flag to any command that need it. To edit the remote server's config, for example:

```bash
rray config -r whatever-name
```
