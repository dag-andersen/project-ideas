# 2: Site Reliability Engineering (22,50 ects)

## What is the problem we are trying to solve?
At my previous workplace, I told my boss, "If I was the CEO of the company, I would not be able to sleep at night if i knew the state of our systems - If our stuff goes down, we have no idea how to start it again" ... and he just laughed at me and said, "Well then it is good that he does not know that". 

Sadly many companies have built infrastructure over the years that they have no idea how to start again if it goes down.
Maybe the system has constantly been running for years, and the people who got it up and running may have left the company or it is just poorly documented.

I want to be able to tell my boss/CEO. "Don't worry, boss, if our systems go down (literally everything is down) I can spin our whole infrastructure up in 15 min."

Kubernetes already has a lot of cool built-in systems with self-healing and health checks, but there is no safety if the whole cluster goes down. I want to make sure that we can also rebuild the whole clusters in no time, should everything go down.

The industry is moving from Pets to Cattle - meaning that we do not treat our systems as pets we need to care about and protect from any danger. Instead, we care about "if the system goes down, can we create a new one?". Treat the infrastructure like something we can just tear down and rebuild in no time. 

(this idea of _Pets vs. Cattle_ is fairly new, and it annoys me that it seems like some seniors in the industry do not seem to think it is possible in practice. I feel very strongly about that. I want to prove that it is possible and should be considered best practice)

## What is the contribution to the world?

> So the question is how to build a reliability and repeatable cloud environment in order to ensure the highest availability and the lowest MTTR?

I want a single command that spins up a production, staging, and testing cloud environment with logging, monitoring, database, service, and GitOps. Everything is fully automated and version-controlled. 

Building a complete modern tech stack fully cloud agnostic/native, based on principles like infrastructure as code.

It is very important that everything is repeatable. I don't want only 90% of it to be repeatable and the last 10% being manual bootstrap afterward. That does not ensure quick recovery if this was a company. We want to be sure that the whole thing can come up in no time.

I claim many companies do not know where to start on this and just start Kubernetes clusters and end up treating them like _pets_. I want to prove that it is possible to build a full repeatable system including everything you need in a modern development environment, so you can treat your environments as _cattle_.

The system should not only be resilient to container/server crashes, but it should also be resilient to complete shutdowns. 

I want to prove that such a system can be done and should be the standard for all new systems.

## Notes
- This idea originates from me being annoyed by the infrastructure at my old workplace. They used Kubernetes and they did many things right - but I believe they could do better! So I tried to ask myself how I would build the perfect infrastructure/development environment in 2022?

- I did a mini version of this in my free time last summer, but I would like to extend it to include everything a modern development environment requires.

- The scope of this project can easily be scaled up and down depending on how much time I have.