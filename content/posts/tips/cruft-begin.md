---
title: "Cruft, CookieCutter for newbie 🌟"
date: 2022-08-07T00:00:00+07:00
description: "The solution for template project."
tags: [tips]
---
Current issue:

    Currently, we using the Bitbucket server for `Source Code Management`.
    In this your project, you have 10 repositories.
    For each repository is include `shared` folder. It's mean the same folder.
    And now if I want to change something in `shared` folder in repository A0.
    I must change all repositories (from repo A1 --> repo A9) manually. 
    And I must create 9 PRs for this change. 😱😱😱😱.

**Solution:**

    In this case, we have 2 options:
        1. Submodule
        2. Cruft
    And today, I will talk about option 2 - Cruft.

⭐⭐⭐ **Important**

    I just introduce about case that we already have existing repositories.
    We have more and more tutorials for case create new repository with this mechanism.

==========================================================================================================

************************************************************************************************

## Concept overview ## 🍌🍌🍌

***1️⃣ Install the cruft***

To get started - install cruft using a Python package manager:

    pip3 install cruft
    OR
    poetry add cruft
    OR
    pipenv install cruft

***2️⃣ Making the repository to TEMPLATE***
Create folder template include all files need to sharing.

    cookiecutter-component/
    ├── {{ cookiecutter.directory_name }}/  <--------- directory template
    │       └── ...
    ├── blah.txt                      <--------- Non-templated files/dirs
    │                                            go outside
    │
    └── cookiecutter.json             <--------- Prompts & default values

In ***cookiecutter.json***

    {
        "directory_name": "shared"
    }

***...continus... waiting***
