---
title: Changes
linktitle: Changes
type: docs
description: The change log for Jenkins X 3.x
weight: 55
aliases: 
    - /v3/about/changes/
---

You may also find the [Roadmap](/community/roadmap/) and [Maturity Matrix](/v3/about/maturity-matrix/) documents useful:


## Pre beta changes

## Changes 


* The [3.0 beta is almost ready](/blog/2020/12/04/jx-v3-update/) so if you have been using the 3.0 alpha we now have a [migration guide](/v3/admin/guides/migrate/v3-alpha/) to smooth your transition to the beta

* You can now easily open the [Octant Console](/v3/develop/ui/octant/) or [Pipeline Dashboard](/v3/develop/ui/dashboard/) via 2 easy commands:

```bash 
jx ui
jx dash
```    

* We now have [Tekton Catalog integration](/v3/develop/pipeline-catalog/) so that you can:
  * easily [edit any pipeline in any git repository](/v3/develop/pipeline-catalog/#editing-pipelines) by just modifying the `PipelineRun` files in your `.ligthhouse/jenkins-x` folder
  * [reuse Tasks from the Tekton catalog](/v3/develop/pipeline-catalog/#adding-tasks-from-the-tekton-catalog) and optionally modify them locally in your repository
  * [add new pipelines to any git repository](/v3/develop/pipeline-catalog/#add-new-taskspipelines-by-hand) to reuse any `PipelineRun` files you find from places like the [tekton catalog](https://github.com/tektoncd/catalog) into your repositories

* We have migrated most of the [Jenkins X Plugins](https://github.com/jenkins-x/jx-cli#plugins) over to the new client-go 1.19.x version now which is a fairly major change due to the API changes in client-go. So we've moved many of the [libraries](https://github.com/jenkins-x/jx-cli#libraries) over to use `v3` instead such as using libraries like [jx-api](https://github.com/jenkins-x/jx-api) or [jx-helpers](https://github.com/jenkins-x/jx-helpers)
  * if you were planning on submitting a Pull Request on any plugin please make sure you rebase before submitting a Pull Request. Also upgrade to go `1.15.2` ASAP 
  
* New [Maturity Matrix](/v3/about/maturity-matrix/) published! You can now view at a glance the different capabilities across clouds and infrastructure. Many thanks [Nitin](https://github.com/borntorock) for all your hard work

* Preview environments how use [helmfile](https://github.com/roboll/helmfile) as a declarative way to describe all of the dependencies you need in your preview environment. 

  * This is all handled by the new [jx-preview](https://github.com/jenkins-x/jx-preview) plugin
  * This also opens up the possibility of using multiple namespaces per preview; or using canary releases on multiple previews into a shared environment.
  
* The new Jenkins X version 3 CLI [jx-cli](https://github.com/jenkins-x/jx-cli) is now plugins all the way down; so that all of the features are implemented by [separate binary plugins](https://github.com/jenkins-x/jx-cli#plugins) making the CLI more modular and easier to work on.