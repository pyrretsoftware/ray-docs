---
icon: sliders-up
---

# Creating your project config

Your project config, also called your `ray.config.json` file is a file that lives in the root of your project's git repository that tells ray **how** to deploy your project. The most important part of your project config is called your project's **pipeline**, which is a series of instructions or commands that specifies steps to build and deploy your project. See the example config below:

{% code title="ray.config.json" %}
```json
{
  "Version" : "v1",
  "Pipeline" : [
    {
      "Tool" : "npm",
      "Command" : ["install"],
      "Type" : "build"
    }, 
    {
      "Tool" : "node",
      "Command" : ["index.js"],
      "Type" : "deploy"
    }
  ]
}
```
{% endcode %}

Here, ray will look for an executable file called "npm" in your system's PATH, then execute it with the argument "install". The type tells ray if the command is just part of the build process or if it is the command that actually starts your application. In this case, the first pipeline step will be identical to running `npm install` , but note that this often wont be the case, since nothing is ever being passed to the shell (for example, piping and command chaining wont work).

{% hint style="success" %}
There are also some built-in tools. For example, the "rayserve" tool will automatically statically serve the root directory of your application!
{% endhint %}

