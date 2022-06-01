# Reading_Notes
## Code 401 - Advanced Software Development





By [Ghaida Al Momani] (https://github.com/GhaidaMomani).


<br/>
<hr/>
<br/>

# API Deployment 


## Configuring Django Settings: Best Practices
[Link to the article](https://djangostars.com/blog/configuring-django-settings-best-practices/)



## Managing Django Settings: Issues
Different environments. Usually, you have several environments: local, dev, ci, qa, staging, production, etc. Each environment can have its own specific settings (for example: DEBUG = True, more verbose logging, additional apps, some mocked data, etc). You need an approach that allows you to keep all these Django setting configurations.

Sensitive data. You have SECRET_KEY in each Django project. On top of this there can be DB passwords and tokens for third-party APIs like Amazon or Twitter. This data cannot be stored in VCS.

Sharing settings between team members. You need a general approach to eliminate human error when working with the settings. For example, a developer may add a third-party app or some API integration and fail to add specific settings. On large (or even mid-size) projects, this can cause real issues.

Django settings are a Python code. This is a curse and a blessing at the same time. It gives you a lot of flexibility, but can also be a problem – instead of key-value pairs, settings.py can have a very tricky logic.



## Setting Configuration: Different Approaches
There is no built-in universal way to configure Django settings without hardcoding them. But books, open-source and work projects provide a lot of recommendations and approaches on how to do it best. Let’s take a brief look at the most popular ones to examine their weaknesses and strengths.

settings_local.py
This is the oldest method. I used it when I was configuring a Django project on a production server for the first time. I saw a lot of people use it back in the day, and I still see it now.

The basic idea of this method is to extend all environment-specific settings in the settings_local.py file, which is ignored by VCS.


12 Factors
12 Factors is a collection of recommendations on how to build distributed web-apps that will be easy to deploy and scale in the Cloud. It was created by Heroku, a well-known Cloud hosting provider.

As the name suggests, the collection consists of twelve parts:
```
Codebase
Dependencies
Config
Backing services
Build, release, run
Processes
Port binding
Concurrency
Disposability
Dev/prod parity
Logs
Admin processes
```
Each point describes a recommended way to implement a specific aspect of the project. Some of these points are covered by instruments like Django, Python, pip. Some are covered by design patterns or the infrastructure setup. In the context of this article, we are interested in one part: the Configuration.

Its main rule is to store configuration in the environment. Following this recommendation will give us strict separation of config from code.

You can read more on 12factor.net.

django-environ
Based on the above, we see that environment variables are the perfect place to store settings.

Now it’s time to talk about the toolkit.

Writing code using os.environ could be tricky sometimes and require additional effort to handle errors. It’s better to use django-environ instead.

<hr/>
<p align="right">(<a href="#top">back to top</a>)</p>
<br/><br/>



# What Is SSH: Understanding Encryption, Ports and Connection
[Link to the article](https://www.hostinger.com/tutorials/ssh-tutorial-how-does-ssh-work)


SSH, or Secure Shell Protocol, is a remote administration protocol that allows users to access, control, and modify their remote servers over the internet.

SSH service was created as a secure replacement for the unencrypted Telnet and uses cryptographic techniques to ensure that all communication to and from the remote server happens in an encrypted manner. It provides a mechanism for authenticating a remote user, transferring inputs from the client to the host, and relaying the output back to the client.

The example below shows a typical SSH prompt. Any Linux or macOS user can SSH into their remote server directly from the terminal window. Windows users can take advantage of SSH clients like Putty.  You can execute shell commands in the same manner as you would if you were physically operating the remote computer.
















<hr/>
<p align="right">(<a href="#top">back to top</a>)</p>
<br/><br/>
<p align="right">Ghaida Al Momani, Software Engineer</p>
<p align="right">Jordan, Amman</p>
  <p align="right">22, 31 May </p>