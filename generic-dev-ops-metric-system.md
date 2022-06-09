# Generic DevOps Metric system

Problem:

DORA have 4 key metrics (and a 5th) that measure how good you are at DevOps.
link: [thenewstack](https://thenewstack.io/dora-2019-devops-efforts-improving-but-not-done/) and [devops-research](https://www.devops-research.com/research.html).
Updated source from 2021: [Link](https://services.google.com/fh/files/misc/state-of-devops-2021.pdf)

Problem is, that it is hard to do the collection of these metrics on a generic (non-specific) environment.

Research question: Is it possible to construct and maintain a collection of metrics that independent of your software toolstack can measure these five metrics?

Could limit the ops part to Cloud native to make sure that you get some of that in as well (and who does not like cloud native, right?!)


More sources:
- https://www.swarmia.com/blog/dora-metrics/


# Metrics

## Deployment frequency
- track image updates
- something that counts pull request

## Lead time for changes
- time for first commit on a branch until it is merged + the time it takes to roll out the deployment.

## Time to restore service
- Using a external monitoring tool like datadog. E.g sending ping every minute.
- Depends on we are talking all services at once or we at just talking a single service
- an operator that that checks how often a service is unhealthy props
- an operator that pings the services and stores it as a statefulset

## Change failure rate
- count rollback to old images
- Count pull request with hotfixes in name.
- problem is detecting if a pr is a hotfix or just an small update. Like what is a failure in deployment?


