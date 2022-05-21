
# Reading_Notes
## Code 401 - Advanced Software Development





By [Ghaida Al Momani] (https://github.com/GhaidaMomani).


<br/>
<hr/>
<br/>

# Docker
* [A Beginner's Guide to Docker](https://wsvincent.com/beginners-guide-to-docker/)  
**Docker** is a set of platform as a service products that use OS-level virtualization to deliver software in packages called containers. The service has both free and premium tiers. The software that hosts the containers is called Docker Engine. It was first started in 2013 and is developed by Docker,

## Docker Architecture 
![](../assests/Docker_Architecture.png)

# When To Use Docker?
```
Docker is a basic tool, like git or java, that you should start incorporating into your daily development and ops practices.

Use Docker as version control system for your entire app's operating system
Use Docker when you want to distribute/collaborate on your app's operating system with a team
Use Docker to run your code on your laptop in the same environment as you have on your server (try the building tool)
Use Docker whenever your app needs to go through multiple phases of development (dev/test/qa/prod, try Drone or Shippable, both do Docker CI/CD)
Use Docker with your Chef Cookbooks and Puppet Manifests (remember, Docker doesn't do configuration management)
```
# What Isn't Docker?
Before we talk about what Docker is, I will talk about what it isn't. What is the negation of Docker? What are its limits? What can't Docker do?

* Docker is NOT a Linux Container technology (like LXC)
* Docker is NOT limited to just LXC anymore (can theoretically manage VMs in the future)
* Docker is NOT a Configuration Manager replacement (like Chef, Puppet, SaltStack, etc)
* Docker is NOT a PaaS
* Docker is NOT good at linking across separate servers or VMs (yet, see ambassadors)
* Docker is NOT good at isolating Linux Containers from each other (shared kernel)

<br/>

**[Useful Link](https://www.ctl.io/developers/blog/post/what-is-docker-and-when-to-use-it/)**

<hr/>
<p align="right">(<a href="#top">back to top</a>)</p>




# Containers vs Virtual Environments

![](../assests/containers-vs-virtual-machines.jpg)
If you are a Python programmer (like me) a common question at this point is, what about virtual environments? How do they differ from containers?

Virtual environments are used to isolate Python software packages locally. We can create an isolated box for individual projects so one can use Python 2.7 and Django 1.5 while another can use Python 3.5 and Django 2.1 on the same computer. Virtual environments are great.

But…virtual environments can only isolate Python packages. They still rely on a global, system-level installation of Python albeit they can refer to the proper version. So when we use Python 2.7 in a project, we’re pointing to an installation of Python 2.7 on the computer itself, not actually within the virtual environment.

Also we can’t run a production database or other services within virtual environments so compared to Docker containers they are far more limited.


# APIs
[Link](https://djangoforapis.com/library-website-and-api/)






















<hr/>
<p align="right">(<a href="#top">back to top</a>)</p>





  <br/><br/>

<p align="right">Ghaida Al Momani, Software Engineer</p>
<p align="right">Jordan, Amman</p>
  <p align="right">22, 21 May </p>