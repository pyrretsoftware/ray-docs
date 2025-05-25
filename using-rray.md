---
description: Installing and using rray (remote ray)
icon: chart-network
---

# Using rray

Rray is a tool used to easily communicate with remote ray servers. It's designed to run on development machines and builds are available for almost every platform.&#x20;

### Installation

Rray can easily be downloaded through through pyrret's package server. You can navigate to [pkgs.pyrret.com](https://pkgs.pyrret.com/) and find a binary by choosing your OS and processor architecture. You usually want rray installed in `/usr/bin` on Linux or Macos and `%%USERPROFILE%%` on Windows, so see the commands below depending on your platform.

On Linux/Macos, if you have wget installed:

```bash
cd /usr/bin && wget "https://pkgs.pyrret.com/linux/ARCH/rays"
```

Making sure to replace ARCH with your actual processor architecture (386, amd64, arm64)

On Windows, using powershell:

```batch
cd %%USERPROFILE%% && wget "https://pkgs.pyrret.com/windows/amd64/rays"
```

Making sure to replace amd64 if you're running 32 bit Windows or Windows for arm.

{% hint style="info" %}
On Windows, make sure to add %%USERPROFILE%% to your path variable, that way you can use the rray command everywhere.
{% endhint %}

If rray isn't available for your platform on our package server, you can also build it yourself. Rray compiles to any operating system and architecture supported by golang, so just clone the ray repository and run `go build` in the rray directory. A binary named `rray` or `rray.exe` will be produced.

### Adding a remote

Now it's time to actually use rray. First up, you'll need to make sure the remote server you're connecting to accepts connections over ssh and that you have ssh authentication for that server. If you are authenticating via a public key, rray will use the key already stored on your system. If you are using a  password, you'll have to enter the password when adding the remote and ray will automatically use that every time you connect.

To add a remote, type `rray remote add` and fill in the fields until you're done, giving the remote a name, hostname (domain or ip), as well as adding one or more authentication methods.

### Connecting to the remote server

To connect to the remote server, specify it's name as the `r` flag to any command that requires it. To edit the remote server's config for example, run:

```bash
rray config -r whatever-name
```
