---
description: Docs for the project config
icon: rectangle-history
---

# Project

### Src `string`

Src specifies the **source** of your project, that is a git repository to fetch from, for example `https://github.com/pyrretsoftwarelabs/ray-demo`&#x20;

### Name `string`

Name specifies a unique name for your project.

### EnvVars `map[string][string]`&#x20;

EnvVars is a list of environment variables to be passed to all commands in this projects deployment pipeline. Use this for things for secret values like database logins, API keys, etc.

### Domain `string`&#x20;

Domain specifies a host your project should be accessible at. It is matched by ray router against the [HTTP host header](https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/Host), so it should not include a protocol, for example: `test.axell.me` .

### Deployments `[]deployment`&#x20;

Deployments specifies your project's [deployments](../../guides/deploying-a-project/extending-your-project-with-more-ray-features.md#different-deployments).

### PluginImplementation `string`&#x20;

PluginImplementation specifies that the project implements a plugin, which tells ray to pass data from a plugin to this project in the `x-ray-plugin-data` HTTP header.

### Options `map[string]string`&#x20;

Options is a list of special options that isn't always available. The list changes frequently, so it won't be written out here.

### DeployOn `[]string`&#x20;

List of names of the RLS helper servers to deploy this project to. Use "local" to specify the current server. Default value is \["local"]

### ProdTypeIsDev `bool`&#x20;

Whether or not to treat the `prod` channel of this project as a deployment with type `dev` (that is, require authentication)
