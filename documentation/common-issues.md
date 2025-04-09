---
description: Common issues you may run into
icon: circle-exclamation
---

# Common issues

## Authenticating when using private repos

When using private repos, you'l need to make sure your authenticated with git on your server. Remember that rays runs as root, so you need to make sure you are authenticating git as the root user. For example, when authenticating with GitHub, you need to run `sudo gh auth login` instead of `gh auth login` if you're logged in as a regular user.

If you want automatic updates to your project as the origin git repository changes, you'l also need to specify Git authentication with the `GitAuth` config option like so:

<pre class="language-json"><code class="lang-json">"GitAuth" : {
    "Username" : "",
<strong>    "Password" : ""
</strong>}
</code></pre>

This will use HTTP basic authentication when connecting to your git server. Some git providers require tokens instead of a password in the password field, like GitHub, where you need to use a [Personal Access Token](https://docs.github.com/en/rest/authentication/authenticating-to-the-rest-api?apiVersion=2022-11-28#authenticating-with-a-personal-access-token).
