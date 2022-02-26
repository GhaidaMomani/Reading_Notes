# How to Setup an Awesome Python Environment for Data Science or Anything Else
Read: Calss01

## Introduction
Coding in Python is awesome and is getting more awesome with every new release! For me, this is mainly due to the massive amount of freely available libraries, its readability, and the recently introduced type annotations. However, especially we as Data Scientists tend to often produce big and messy Jupyter notebooks or python files that are hard to follow. Apart from that, we often run into version clashes when one project depends on a different version fo the same library. Fixing this takes too much time and often leads to issues with other projects. There must be a way to avoid that and facilitate our lives. In this article, I will go through the tools that I use and the techniques that I usually follow. This hopefully will help future me to remember all of that, and more importantly, will help you also learn something helpful. Without further ado, let’s get our hands dirty.
The Python Environment
The Interpreter
Let’s get started with the most important thing when working with python: the interpreter. For sure you could just simply download and install your favorite version of python and put everything into that. But what if you have programs that require different python versions or programs that depend on different versions of the same third-party module and you want to switch between those programs seamlessly?
Pyenv will help you doing that!
Pyenv is a set of three tools, from which I present two here, that are pyenv (used to install python) and pyenv-virtualenv (used to configure your global tools). You can install them by

```curl https://pyenv.run | bash```

After that, add the following lines to your .bashrc (same for .zshrc) to have pyenv available in your terminal

``export PATH="~/.pyenv/bin:$PATH"``
``eval "$(pyenv init -)"``
`eval "$(pyenv virtualenv-init -)"`


and finally, restart your terminal. If you are a mac user, you can of course use brew to install pyenv.
Now, you can use pyenv to install almost any python interpreter, including pypy, and anaconda. Note, that pyenv builds python locally on your machine. Building python requires several libraries. On my Ubuntu machine, I have to install the following ones to not run into problems
sudo apt-get install build-essential libsqlite3-dev sqlite3 bzip2 libbz2-dev zlib1g-dev libssl-dev openssl libgdbm-dev libgdbm-compat-dev liblzma-dev libreadline-dev libncursesw5-dev libffi-dev uuid-dev
Now, to install a python interpreter just do
pyenv install VERSION_YOU_WOULD_LIKE_TO_INSTALL
You can list out all versions available via pyenv

`pyenv install --list`

To make it concrete, let’s install python 3.7.5 and make it your default global-interpreter

`pyenv install 3.7.5`
`pyenv global 3.7.5`

When you type python — version you should get back Python 3.7.5
Dependency Management
Managing project dependencies in python can become messy or manual. There exists a bunch of tools to help you with that.
The one that I use the most is poetry.
Apart from many other things, poetry helps you to easily
manage your projects’ dependencies,
separate your projects through virtual environments,
build both applications as well as libraries without headaches.
The way the authors recommend installing poetry is
curl -sSL https://raw.githubusercontent.com/sdispater/poetry/master/get-poetry.py | python
Another way, that I am going to show you is using pip and pyenv-virtualenv. You may ask: Why not just pip? Because this would install poetry and its dependencies in your global environment, which you probably don’t need there and also don’t want there. So, here are the necessary commands
# Create a virtual environment called tools that is based on 3.7.5
`pyenv virtualenv 3.7.5 tools` 
# Install poetry into the tools virtual env
```pyenv activate tools```

```pip install poetry```
# Check installed poetry version
```poetry --version```
# Leave the virtual env 
```pyenv deactivate``` 
# This does not work yet 
`poetry --version`
# Add your tools virtual env to the globally available ones
```pyenv global 3.7.5 tools```
# Now this works and you can start using poetry
```poetry --version```
Before we start using poetry to create our first project I recommend configuring it, such that it creates your project’s virtual environment in a .venv folder inside the project directory. This is very handy when you are using IDEs like VS Code or PyCharm as they immediately recognize that and pick up the correct interpreter
# That seems to be peotry prior to 1.0.0
```poetry config settings.virtualenvs.in-project true```
# That is poetry since 1.0.0
`poetry config virtualenvs.in-project true`

Note that, you only have to set this configuration once, as its set globally and persisted.
Finally, we have everything in place to create our first project using poetry, Awesome! I call this project dsexample, a stupid name I know but I did not want to waste even more time finding a better one. To show you how to use poetry, I add pandas in a specific version and fastapi with all extra requirements
# Initialze a new project
`poetry new dsexample `
`cd dsexample`
# Add modules and create virtual environment.
`poetry add pandas=0.25 fastapi --extras all`
# As an example of how you could add a git module
poetry add tf2-utils --git git@github.com:Shawe82/tf2-utils.git
If you want to see a real project using everything I present you here, please go to my Github Repo.
Consistent Formatting and Readability
Now, as we have created our project, we will start working on it adding more and more code to it. Ideally, your codebase is formatted consistently to ensures readability and understandability. This can become a very tedious process, especially if you are not the only person working on the codebase.
Black to the rescue!
Black is a tool for python that allows you to focus on what is necessary, the content. It does that by freeing you from manual code formatting through automation. As it is so nice, let’s add it to our dsexample project and let’s format all files
# We add black as a development dependency with --dev as we don't
# need it when it comes to production
`poetry add --dev black=19.3b0`
# Assume we are inside the current toplevel dsexample folder
poetry run black .
Nice, all the files look very good now.
Type-Correctness
Since Python 3.5, please correct me if I am wrong, type annotations are part of the standard library. Through type annotations, your code becomes better to understand, maintain, and less prone to errors. Why less prone to errors? Because you can statically check if the types of your variables and functions match the expected ones. For sure this has to be automated
and here comes mypy!
Mypy is a static type checker for python code, that finds errors before they appear. Adding mypy and type-checking to your project using poetry is as easy as adding black
# We add mypy as a development dependency with --dev as we don't
# need it when it comes to production
`poetry add --dev mypy`
# Assume we are inside the current toplevel dsexample folder
poetry run mypy .
Running mypy might create a lot of errors. For sure you can configure it to only warn you about the things you are interested in. You do that by adding a mypy.ini file to your project and refer you and future me to the documentation for more details.
Automate the Automation
With black and mypy we can avoid formatting code manually or run into avoidable errors. But, we still have to execute those tools manually. Shouldn’t that be automated too? Yes!
Pre-commit is all you need.
Pre-commit is a tool that executes checks before you commit code to your repository (I took for granted that your code is under git version control). When those checks fail, your commit will be rejected. With that, your repository will never see mall formatted code, or none type-checked one, or anything else depending on the checks you are going to include. So let’s install pre-commit.
You can either install it directly into your project using poetry or install it on your local machine. I prefer the latter, as pre-commit is only used locally and not on a CI/CD server. In contrast, black and mypy should run on a CI/CD server, thus, it makes sense to add them to the project’s dev dependencies. Here is how I suggest installing it making use of the already existing tool virtual environment
# Install pre-commit into the tools virtual env
`pyenv activate tools`
`pip install pre-commit `
# Leave the virtual env 
`pyenv deactivate`
# As we have already added the tool venv, it will work directly
`pre-commit --version`

To use it, you first need to add a config file called .pre-commit-config.yaml to the top-level folder of your project. In that file, you configure all the hooks that should run. With mypy and black, this file looks like
repos:
-   repo: https://github.com/ambv/black
    rev: 19.3b0
    hooks:
    - id: black
      language_version: python3.7
-   repo: https://github.com/pre-commit/mirrors-mypy
    rev: v0.740
    hooks:
    - id: mypy
Last, you must tell pre-commit to set up the hooks by executing
# I assume your are in the top level folder
2pre-commit install
Now, the hooks will run on every commit. The black hook will not only check for formatting issues but also format the files accordingly. Whenever you add a new hook, so also at the very beginning, it is recommended to manually run pre-commit on all files as is it only touches the files that have been changed since the last commit
pre-commit run --all-files
And that’s it, we have automated the automation!
Wrap Up
There are many tools around that help you focus on what is important. Here, I have presented you only a couple and for sure, there are others and many more. Hopefully, you’ve learned something new and can focus on content. Thank you for following along and feel free to contact me for questions, comments, or suggestions.

  <br/><br/>
<hr/>
<p align="right">Ghaida Al Momani, Software Engineer</p>
<p align="right">Jordan, Amman</p>
  <p align="right">22, 26 Feb </p>