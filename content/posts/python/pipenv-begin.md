---
title: "How to use pipenv ?"
date: 2022-06-01T12:13:32+05:30
description: "Pipenv is a packaging tool for Python that solves some common problems associated..."
tags: [python, pipenv]
---

## Basic Concepts

1. Pipenv is a python package manager which gives programmers better control over their pip project dependencies.

2. Pipenv allows you to select the specific version of python, and the versions of the pip packages required.

3. For those that are familiar with JavaScript development, pipenv can be thought of as the python equivalent of npm.

## How to install pipenv

    pip install --user pipenv
    //
    pip3 install --user pipenv
    ----------------------------
    OR UPDATE
    pip install --user --upgrade pipenv
    //
    pip3 install --user --upgrade pipenv

Note: If you have issue `zsh: command not found: pipenv`.

Calm down and execute this command.

    sudo -H pip install -U pipenv

## How to **UNDERSTAND** pipenv

Create a new project (new folder), It can be empty.  
In this case, we will create a new project with name==first_pipenv

    cd first_pipenv  
    pipenv install requests

In this step, we will create a new environment.  
And in new environment, we also installed `request` package.

In this folder==first_pipenv, we can see the 2 files:

1. **Pipfile**  

    - It will be auto generated with command `pipenv   install`.
    - It will be auto input the `request` package.

    **Example**
        [[source]]
        url = "https://pypi.org/simple"
        verify_ssl = true
        name = "pypi"

        [packages]
        requests = "~=2.5.0"

        [dev-packages]

        [requires]
        python_version = "3.9"

2. **Pipfile.lock**  

    - It will takes advantage of some great new security improvements in pip.
    - It will be generated with the sha256 hashes of each downloaded package.
    - They highly recommend approaching deployments with promoting projects from a development environment into production.

    **Example**
        {
            "_meta": {
                "hash": {
                    "sha256": "a736cf9dd2af80d1feeff6d44e39c1f78c1b7825370f57af5b87ec82e6a8c724"
                },
                "pipfile-spec": 6,
                "requires": {
                    "python_version": "3.9"
                },
                "sources": [
                    {
                        "name": "pypi",
                        "url": "https://pypi.org/simple",
                        "verify_ssl": true
                    }
                ]
            },
            "default": {
                "requests": {
                    "hashes": [
                        "sha256:3e66d7ba78e7a6a8eccd2e901079ab8d24e408b5375cf32eb51f291306302418",
                        "sha256:55d7f5619daae94ec49ee81ed8c865e5a2a47f0bbf8e06cf94636bee103eaf65"
                    ],
                    "index": "pypi",
                    "version": "==2.5.3"
                }
            },
            "develop": {}
        }

***NOTE***

1. If you change the version or something in `Pipfile`. Then you must execute the command `pipenv install` to update the `Pipfile.lock`.
2. If you want to install 20 packages in your environment. You will execute list command:
    ```
        pipenv install package_A
        pipenv install package_B
        pipenv install package_C
        pipenv install .........
    ```

This is stupid solution.

And you just add list packages in the `Pipfile` ---> execute the command `pipenv install` ---> everything **DONE**

## How to **KNOWN** You are a superman

It's mean how to know your new environment is correct ?
We have more method to check it.

**Exampl:**

    pipenv run pip freeze
    //output
    requests==2.5.3

    pipenv shell ## you already exec the new environment
    pip freeze
    //output
    requests==2.5.3

***IT's OK***
Thanks for your reading. I hope it's useful to you.

**Document to more detail *[Pipenv](https://pipenv-fork.readthedocs.io/en/latest/basics.html)*.**