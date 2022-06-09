# 3: Chaos Engineering (22,50 ects or Thesis)

Chaos Engineering is the discipline of experimenting on a system in order to build confidence in the system’s capability to withstand turbulent conditions in production. In 2011, Netflix created the project called Chaos Monkey, which kickstarted the Chaos Engineering discipline.

*This is my absolute favorite topic when it comes to Computer Science.*

## What is the problem we are trying to solve?

Chaos Engineering is a relatively new concept, and it is far from standardized yet. 

Netflix's original Chaos Monkey is a general-purpose Chaos Monkey. Since the industry is slowly moving to Kubernetes, it would be convenient if there were a good Kubernetes specialized solution to that. 

There exist a tool called [Litmus](https://litmuschaos.io/) (maintained by CNCF) that tries to solve this problem. It tries to apply the principles of Chaos Engineering to Kubernetes. Last summer, I tried installing it on my home cluster, but I found it really difficult to use. 

Chaos Engineering is mainly practiced in big tech like Netflix - I think that is a problem!

Small startups do not have time for a week trying to install a system that "just kills their system at random time intervals". But the problem is that you get the most benefit from Chaos Engineering if you apply it from the start. If you want to ensure you build a resilient system, you want to do it from the absolute beginning of the project to ensure that every single service you build can survive crashes, network issues, memory issues, network issues, etc. You have to think that from the beginning - but that is not happing if it is too complicated to get started!

I would argue that the entry barrier is too high currently. It is too difficult to get started resulting in smaller businesses passing on the idea of chaos engineering. 

## What is the contribution to the world?

> So the question is how do conveniently apply the concept of chaos engineering to a Kubernetes setup in order to ensure resiliency?
Design, Implement and Evaluate a state-of-the-art Choas Engineering cloud setup.

The plan is to set up a Kubernetes cluster, deploy some simple dummy-services, and create an automated Chaos engineering setup.

This can either be done by trying out a tool called Litmus or building a custom setup myself. As explained, I tried using Litmus, but i couldn't get it working, so I started experimenting with building my own. Last summer, I created a project called [khaos-monkey](https://github.com/dag-andersen/khaos-monkey) (take a look, I think it is pretty cool). This is a simple chaos monkey based on the original idea from Netflix. It is very simple, and the only thing it does is crash containers based on a rule-set/configuration. I would like to extend that idea and build it into a proper tool that injects a lot of different faults into the system.

There exist different approaches to this problem. My contribution to the world is a new method of applying chaos to Kubernetes that is (hopefully) easier to install for smaller projects that don't want to spend days trying to figure out how to set up a complex tool like Litmus. 

## Notes

- The problem with this project is that in order to test the Chaos Attacks, you need a fairly comprehensive environment up and running beforehand. You can't test if your systems can survive the chaos if you don't have a system. So I thought it would be best to do this project as a Thesis (following up on ideas [1](idea1.md) or [2](idea2.md)).