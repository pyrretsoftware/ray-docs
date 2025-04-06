---
description: Common issues you may run into
icon: circle-exclamation
---

# Common issues

## Authenticating git when using private repos

When using private repos, you'l need to make sure your authenticated with git on your server. Remember that rays runs as root, so you need to make sure you are authenticating git as the root user. For example, when authenticating with GitHub, you need to run `sudo gh auth login` instead of `gh auth login` if you're logged in as a regular user.
