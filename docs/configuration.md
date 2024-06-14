---
layout: default
title: Estrutura do Projeto
nav_order: 2
---

# Estrutura do Projeto
{: .no_toc }

Estrutura base inicial do projeto.
{: .fs-6 .fw-300 }

You can reference multiple collections.
This creates categories in the navigation with the configured names.

```yaml
collections:
  tests:
    permalink: "/:collection/:path/"
    output: true
  tutorials:
    permalink: "/:collection/:path/"
    output: true

just_the_docs:
  collections:
    tests:
      name: Tests
    tutorials:
      name: Tutorials
```
