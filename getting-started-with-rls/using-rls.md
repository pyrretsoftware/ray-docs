---
icon: sliders-up
---

# Using RLS

Let's get on to actually using RLS. To add a helper server, see the example below:

{% code title="rayconfig.json" %}
```json
{
    "RLSConfig" : {
        "Enabled" : true,
        "Helpers" : [
            {
                "Name" : "other-server", //name used as identifer
                "Host" : "192.168.1.207", //can be a private/public ip or a hostname/domain that resolves to an ip
                "Weight" : 1.4 //explained below
            }
        ]
    },
}
```
{% endcode %}

The most interesting part of the above snippet is the Weight field, which you probably noticed. It's used to specify how many more requests the server should receive relative to the local server, used when some servers are more powerful than others. As mentioned, it's relative to the local server where the local server has a weight of 1. &#x20;

{% hint style="warning" %}
Weights can only have a precision of two decimal points
{% endhint %}

Now, to specify what servers to deploy a project on, see the example below:

{% code title="rayconfig.json" %}
```json
{
    "Projects": [
        {
            "Name" : "example project",
            "Domain" : "example.com",
            "DeployOn" : ["local", "other-server"], //local means the current server
            "Src" : "https://git-provider.com/user/project"
        }
    ],
}
```
{% endcode %}
