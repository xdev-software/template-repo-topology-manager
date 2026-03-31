[![Distribution Workflow](https://img.shields.io/github/actions/workflow/status/xdev-software/template-repo-topology-manager/distribute.yml?branch=master&label=distribution)](https://github.com/xdev-software/template-repo-topology-manager/actions/workflows/distribute.yml?query=branch%3Amaster)
# (Template) Repo Topology Manager

Distributes hierarchial repo updates (from templates) through the topology

## How can this be used?

### In a normal repo

1. Add the bot account to the repository (write permissions are sufficient)
2. The file `.config/topo/upstream.yml` must exist. It can look like this:
  ```yaml
  - url: https://github.com/xdev-software/standard-maven-template.git
    branch: master
  ```

### In a template

When inside a template the `.config/topo/upstream.yml` needs to be located in the `template-upstream/<org>/<repo>` branch.<br/>
This is required because the default branch's `.config/topo/upstream.yml` is used by the the downstream repositories.


## Template-Overview
_As of 2026-03_

```mermaid
graph TD;
  base[<a href="https://github.com/xdev-software/base-template">base</a>] --> java
  java-setup[<a href="https://github.com/xdev-software/java-setup-template">java-setup</a>] --> java[<a href="https://github.com/xdev-software/java-template">java</a>]
  java --> intellij-plugin[<a href="https://github.com/xdev-software/intellij-plugin-template">intellij-plugin</a>]
  java --> standard-maven[<a href="https://github.com/xdev-software/standard-maven-template">standard-maven</a>]
  standard-maven --> vaadin-addon[<a href="https://github.com/xdev-software/vaadin-addon-template">vaadin-addon</a>]
  standard-maven --> openapi-client-maven[<a href="https://github.com/xdev-software/openapi-client-maven-template">openapi-client-maven</a>]
```
