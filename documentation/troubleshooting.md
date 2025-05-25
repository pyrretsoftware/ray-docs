---
description: Troubleshooting information
icon: triangle-exclamation
---

# Troubleshooting

### Fatal ray error

Often indicated by:

* &#x20;A "ray server has exited" message if you have setup monitoring with Discord/Slack.
* A "Rays did not indicate success in reloading processes" message if the error occurs while reloading
* Rays not answering any requests.

To troubleshoot a fatal error, read the crash.txt file in ray-env. On Linux, for example:

```bash
cat /usr/bin/ray-env/crash.txt
```

This will tell you a crash reason. See [common issues](common-issues.md).

### Process error

Often indicated by:

* A "Process x, deployment y has errored!" message if you have setup monitoring with Discord/Slack.
* A ray error page when accessing a project.

To troubleshoot a process build error, read the log file which is easiest done with the `rray logs` command. If you're not using rray, you can also get the path to the log file with `rays list` .

If the build succeeded, the error occurred after build. This is quite hard to troubleshoot, but try looking at rays's logs with `journalctl` .

