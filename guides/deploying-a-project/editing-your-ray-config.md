---
icon: server
---

# Editing your ray config

Finally, you'l need to add your project to your ray config. See the example below:

```json
{
    "Projects" : [
        {
            "Name" : "new-project",
            "Src" : "https://github.com/username/new-project-repo",
            "Domain" : "localhost"
        }
    ]
}
```

_Name_ is simply a unique name for your project, _Src_ is a link to your project's git repository and _Domain_ tells **ray router** (ray's reverse proxy) what host your project should be accessible at.&#x20;
