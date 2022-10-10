# CI/CD on Github Actions

My naive approach to handling continuous deployment on Github for both any application consists of 3 coordinating branches:
1. `main`- Primary development happens on this branch. Incoming pull requests facilitate trunk-driven development and rapid merging.
2. `staging`- Any work that is ready to move into staging is merged into this branch. 
3. `production`- Production code lives here and a pull request that merges into this branch invokes a production redeploy.

The development process moves from `main` - `staging` - `production`, with the movement of code facilitated by pull requests. By using Github workflows, separate procedures can be defined at each stage of the pipeline. For instance, if separate GCP App Engines are used for staging and production, separate jobs can sequentially push to both. 

In this repository, the following curated workflow templates are available:

1. Node.js on App Engine (Adapted from [@borales](https://github.com/Borales/actions-yarn))
