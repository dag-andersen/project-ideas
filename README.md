# ITU Project Ideas

## Fall 2022

I will write two projects in Fall 2022. A mandatory Research Project (7.5 ects) and an individual project (22,75 ects)

## Spring 2023

I will write my thesis (30 ects)

## Ideas

### 1: Cloud Native (22,50 ects)

#### What is the problem we are trying to solve?

One of the main reasons companies hesitate to fully migrate to the cloud is the fear of vendor lock-in. Ending up being dependent on a specific cloud provider, and making it close to impossible to ever switch provider, because it would be too expensive.

Each cloud provider try to lure the customers into using cool special producst to lock them into their eco system - and it is very temping, because these cool services provider nice benefits - but the problem is that they end up locking them selves in.

This is what CNCF tryes to prevent. Their poppose is to maintain open source technologies that work on all cloud providers.

What you want instead is a fully cloud agnostic setup that you can move from one vendor to another with very little effort. If your current cloud provider increase the price of their service, you should be able to move you systems to another provider.

I claim that most companies do a lot of research on which cloud provider to pick and then expect to stay there for the many years to come. Because they expect it to be very costly to change afterwards.

#### What is the contribution to the world?
> So the question is how can you build a modern software stack in cloud-native technologies to avoid vendor lock-in?
Design, Implement and Evaluate infrastructure required by a modern tech stack in cloud-native technologies that can be deployed to ANY popular cloud provider.

I want vendor-agnostic things like database, microservices, deployment system, and production/staging environment to be easily moved between vendors in order to avoid vendor lock-in.

I want to prove that you can build you systems only using open source cloud native technologies, which you can move between cloud providers without any issues.

### 2: Kubernetes Operators (7,5 ects)
Design, Implement and Evaluate a Kubernetes Operator

Here, the plan is to learn Go and implement a Chaos Monkey (running as a Kubernetes operator).

I am also considering building one in Rust and doing experiments to see which one performs the best. 

### 3: Site Reliability Engineering (22,50 ects)

#### What is the problem we are trying to solve?
At my previous workplace I told my boss "If i was the CEO of the company i would not be able to sleep at night, if i knew the state of the systems - If our stuff goes down we have no idea how to start it again" ... and he just laughed at me and said "Well then it is good that he does not know". 

Sadly many companies have built infrastructure over the years that they have no idea how to start again if it goes down.
Maybe the system has been running constantly for years and the poeple who got it up and running may have left the company or it is just poorly documented.

I want to be able to tell my boss/ceo. "Don't worry boss, if our systems goes down (literally everything is down) i can spin our whole infrastructure up in 15 min."

Kubernetes already have a lot of cool built in systems with self-healing and health checks, but there is no safety if the whole cluster goes down. I want to make sure that we can also rebuild the whole clusters in no time, should everything go down.

The industry is moving from Pets to Cattle - meaning that we do not treat our systems as pets we need to care about and do everything to survive. Instead we care about "if the system goes down, can we create a new one". Treat the infrastructure like something we can just tear down and rebuild in no time.

(this idea is fairly new and it annoys me that it seems like older people in the industry does not seem to think it is possible in practice. I feel very strongly about that i want to prove that it is possible and should be considered best practice)

#### What is the contribution to the world?

> So the question is how to build a repeatable cloud development and production environment in order to ensure the highest possible MTTR/uptime? 

I want a single command that spins up a production, staging, and testing cloud environment with logging, monitoring, database, service, and GitOps. Everything is fully automated and version-controlled. 

Building a complete modern tech stack fully cloud agnostic/native, based on principles like infrastructure as code.

It is very important that everything is repeatable. I don't want only 90% of it to be repeatable and the last 10% being manual bootstrap afterwards. That does not ensure a quick recovery if this was a company. We want to be sure that the whole thing can come up in no time.

I claim many companies do not know where to start on this and just a start kubernetes clusters and end up treating them like _pets_. I want to prove that it is possible to build full repeatable system including everything you need in a modern development enviroment, so you can treat your environments as _cattle_.

The system should not only be resilient to container/server crashes, but it should also be resilient for complete shutdowns. 

I want to prove that such a system can be done and should be the standard for all new systems.

#### Notes
- This idea originates from me being annoyed by the infrastructure at my old workplace. They used kubenretes and they did many things right - but i believe they could do better! I tried to ask myself, how i would build the perfect infrastructure/development environment in 2022.

- I did a mini version of this in my free time last summer, but I would like to extend it to include everything a modern development environment requires.

- The scope of this project can easily be scaled up and down depending on how much time I have.

### 4: Chaos Engineering (22,50 ects or Thesis)

Chaos Engineering is the discipline of experimenting on a system in order to build confidence in the system’s capability to withstand turbulent conditions in production. In 2011, Netflix created the project called, Chaos Monkey, which kickstarted the Chaos Engineering discipline.

This is my absolute favorite topic when it comes to Computer Science.

#### What is the problem we are trying to solve?

Chaos Engineering is a relatively new concept and it is far from standardized yet. 

Netflix's original Chaos Monkey is a general purpose Chaos Monkey. Since the industry is slowly moving to Kubernetes, it would be fitting if there were a good solution to that. 

There exist a tool called [Litmus](https://litmuschaos.io/) (maintained by CNCF) that try to solve this problem. It tries to apply the principles of Chaos Engineering to kubernetes. Last summer i tried installing it on my home cluster, but i found it really difficult to use. 

Chaos Engineering is mostly practiced in big tech like Netflix - I think that is a problem!

Small startups do not have time to a week on trying to install a system that "just kills their system at random time intervals". But the problem is that you get the most benefit from Chaos Engineering if you apply it form the start. If you want to ensure you build a resilient system you want to to do it from the absolut beginning so you ensure that every single service you build can survive crashes, network issues, memory issues, network issues, etc. You have to think that in from the beginning - and that is not happing if it is too complicated to get started!

I would argue that the entry barrier is too high currently. It is too difficult to get started resulting in smaller business passing on the idea of chaos engineering. 

#### What is the contribution to the world?

> So the question is how do we build a apply the concept of chaos engineering to a kubernetes setup in order to ensure resiliency?
Design, Implement and Evaluate a state-of-the-art Choas Engineering cloud setup.

The plan is to set up a Kubernetes cluster, deploy some simple dummy-services, and create an automated Chaos engineering setup.

This can either be done by trying out a tool called Litmus or building a custom setup myself. As explained i tried using Litmus but i couldn't get it working so i started experimenting with building my own. Last summer I created a project called [khaos-monkey](https://github.com/dag-andersen/khaos-monkey) (take a look, I think it is pretty cool). This is a simple chaos monkey based on the original idea from Netflix. It is very simple and the only thing it does is crash containers based on a rule-set/configuration. I would like to extend that idea and build it into a proper tool, that injects a lot of different faults into the system.

There exists different approaches to this problem. My contribution to the world is new method of applying chaos to kubernetes that is easier to install for smaller projects that don't want to spend days trying to figure out how to setup a complex tool like Litmus. 

# Notes

- The problem with this project is that in order to test the Chaos Attacks you need a fairly comprehensive environment up and running before hand. You can't test if you systems can survive the chaos if you don't have a system. So I though it would be best to do this project as a follow up on idea 1 or 3.

## Side Goals

- Learn Go

## Interests

- Cloud-Native
- Kubernetes
- Linux
- Container orchestration
- GitOps & Infrastructure as Code
- Site Reliability Engineering
- Chaos Engineering
- Rust
- Go
- Low level stuff like memory management, thread pools, compilers, etc.

## Bachelor's Project 2020
- Supervised by Philippe Bonnet
- The project was about how cache utilization impacts performance when working with memory-mapped files.
- I used it as an "excuse" to learn Rust (Which is now my favorite language)
- [Report Link](https://github.com/dag-andersen/Rust-Memory-Map/blob/master/docs/Bachelor_Report.pdf)
