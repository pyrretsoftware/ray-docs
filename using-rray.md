---
description: Installing and using rray (remote ray)
icon: chart-network
---

# Using rray

Rray is a tool used to easily communicate with remote ray server. It's designed to run on development machines and builds are available for almost all platforms.&#x20;

### Installation

<details>

<summary>Linux</summary>

Binaries are [available on Github](https://github.com/pyrretsoftware/ray/releases).

</details>

<details>

<summary>Windows</summary>

On windows, you can install rray with winget:

```bash
winget install -e --id Pyrret.Rray
```

Binaries are also [available on Github](https://github.com/pyrretsoftware/ray/releases).

</details>

<details>

<summary>MacOS</summary>

Binaries are [available on Github](https://github.com/pyrretsoftware/ray/releases).

</details>

### Adding a remote

First up, you'll need to make sure the remote you're connecting to has an active ssh running that accepts connection and you need to have authentication for that server. If you are authenticating via public key, rray will use the ssh key already stored on your system. If you use a password, you'll have to enter the password when adding the remote and ray will automatically use that.

Type `rray remote add`  and fill in the fields until you're done, giving the remote a name, hostname (domain or ip), as well as adding one or more authentication methods.

### Using the remote

To use the remote, specify it's name as the `r` flag to any command that need it. To edit the remote server's config, for example:

```bash
rray config -r whatever-name
```
