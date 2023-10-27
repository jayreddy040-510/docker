# docker + docker-compose
> a no-frills introduction to containers and container technology by J

### Overview
1. Who is J?
2. What are containers and why should you care?
3. How to implement containerization in your next project
5. How to easily manage containers (Intro to docker-compose)
5. Common docker/docker-compose commands
6. Demo

### Who is J?
i am! next question. haha, only kidding.

*ahem*

hello friends! my name is Jay and im a swe at a company called
[care.coach](https://care.coach). i joined A/a's 16 wk program in june of 2022
and have been at my current company for a year now. in my past life i was a
3rd grade teacher and later a medical school student. i like to help growing
programmers grow and i <3 pickup bball! feel free to connect with me on
twitter/X [@J_SON_Reddy](https://twitter.com/J_SON_Reddy) or
[LinkedIn](https://www.linkedin.com/in/jay-reddy-69538b240/) and i'm happy to
share my story and hear yours. lots of people helped me on this journey and
i am but a singular node in a long linked list of pay it fwd - node.next'ing all
the way over to you!

now, let's talk containers so you can resume.skills.push("docker", "docker-compose")

### What are containers and why should you care?
containers are *virtual* bundles that wrap your application and all of its
dependencies together into a standardized unit for software development. this
process ensures that your app runs consistently across various environments.

consider the following scenario:

you toil day and night to build an application for a take-home project. you submit
said project and finally get a good night's sleep. to your horror, you wake up
the next morning to an email from the recruiter saying that the engineer
couldn't run your project.

*enter meme: "it works on my machine!"*
![works for me!](./img/worksforme.png)

any number of things could have gone wrong: was there a dependency clash btwn
the engineer's local environment and yours? were the ports that you deployed
your services to already occupied on their machine? was he running 128 browser
tabs and he didn't have sufficient memory to run your app? WHAT HAPPENED?!

containerization is a solution to the above problem. thanks to virtualization,
the container allows for *process-isolation* meaning that to your app inside
of the container, there are no other processes running. so, the system's state
will not affect your application inside of a container as much as it would otherwise.
note the wording: *as much as*. containers still use the host machine (your machine's)
resources however they do so in significantly more isolation than running on your
machine without containerization.

you might be wondering: well, can't i just install and run a virtual machine on
my machine and then i have significant process-isolation? that's a good idea; but,
keep in mind that you also need your virtualization solution to be *portable* (so
you can send it in with your take-home project) and *lightweight* so the overhead
of virtualization doesn't affect your app's performance. containers are often
preferred to VM's because the software to manage them is comparatively lightweight
and portable - this is partly due to the fact that containers share their host
machine's OS kernal whereas a VM will spin up a completely new OS instance.

docker is a lightweight, portable containerization solution and the industry standard
when it comes to using containers. many software products that are developed enough
to reach consumers are using docker. and so, it'll serve you well to learn how to
build and coordinate multiple containers at once.

lastly, while some companies are considering the comparative financial implications
btwn microservice vs. monolithic architecture, microservices continue to dominate
the industry. and where do microservices thrive? in docker containers. each microservice
is typically encapsulated in its own container, providing the isolation and independence
that define the microservice architecture.

*xkcd on microservices/docker:*
![xkcd on containers](./img/xkcd_containers.png)

don't let the hat person's criticism deter you! the modern engineer spends
just as much time making sure independent services are "glue(d) together" well
as they do writing code.

### How to implement containerization in your next project
