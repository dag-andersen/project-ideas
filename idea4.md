# 4: (de)scheduling workload (22,50 ects)
## What is the problem we are trying to solve?

- We want to pay the least amount of money for our resources on cloud providers.
- We want our systems to have the highest availability/uptime, and we don't want to compromise on that.
- We want to go for auto-managed solutions, so we don't have to spend time and resources on managing our infrastructure (e.g., Kubernetes cluster) manually.

These 3 goals are in conflict of interest. Optimizing for the lowest cost of cloud resources does not necessarily do not necessarily go hand in hand with auto-scaling solutions. 

By default, Kubernetes does not de-schedule pods the moment they start running. They are only re-scheduled on other nodes if the pod crashes and there are more free resources on other nodes.

That means that you can end up in situations where most of your long-running services are running on a single node because they are never de-scheduled.
This results in an uneven load across nodes, which is more expensive in raw resources because other nodes are underutilized. 

We can probably solve that problem by just crashing pods all with a fixed interval, helping the scheduler to distribute the pods more evenly... But this has a problem... It lowers your availability because your pods die all the time. So the question is ... can we introduce an aggressive de-scheduler mechanism that creates a more even load across nodes WITHOUT lowering the availability of the individual pods/services?

#### Why is running a de-scheduling in Kubernetes not default?
Not all services can handle getting evicted at arbitrary intervals. 

## What is the contribution to the world?

> How much can introducing an aggressive/eager de-scheduler lower the resource-cost on an auto-managed Kubernetes cluster (without lowering the uptime)? 

Solving this problem is not only about implementing a de-scheduler but also about preparing your services to understand how they do a graceful shutdown and how they tell the cluster their current state through health-checks.

Hopefully, this project will answer whether de-scheduling could lower the cost by a significant amount or if it is not worth introducing in a real-world scenario. 

## Why do I like this project?
- Very clear resource to measure - Pure Cost
- Lower-level complexity in scheduling in Kubernetes.
- Working with Kubernetes at my previous workplace made me curious if caring about de-scheduling actually matters in practice or if it I just some nerdy detail that is not worth bothering with at a real company.

## Notes
- I am still debating with myself if the cluster should be auto-managed/scaled or if it is better for the assignment to do manual node managing. 