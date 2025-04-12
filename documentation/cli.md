---
description: Docs for the rays CLI
icon: terminal
---

# CLI

### list

Lists all running projects.

### reload

Reloads all processes, redeploying everything.

### force-renrollment

After a user is enrolled onto a channel, they will stay enrolled on that channel for up to a year as long as the user don't clear their cookies. Running force-renrollment will cause all users who were enrolled into a channel before the time the command was run to be re-enrolled into another channel.

### stop

Stops rays.

### dev-auth

Gives you an authentication key that's valid for 10 minutes for use on deployment channels that require authentication.

### edit-config

Edits the ray config file with nano.
