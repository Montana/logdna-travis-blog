---
title: "LogDNA and Travis CI"
created_at: Fri Dec 31 2021 15:00:00 EDT
author: Montana Mendy
layout: post
permalink: 2021-12-31-logdnatravis
category: news
excerpt_separator: <!-- more --> 
tags:
  - news
  - feature
  - infrastructure
  - community
---

![TCI-Graphics for AdsBlogs (4)](https://user-images.githubusercontent.com/20936398/147834223-7b2558f0-8811-4193-a57c-73edd0c76852.png)

In this short blog we explore LogDNA. LogDNA is a DevOps teams to aggregate all of their system and application logs into a single platform. Automatic parsing, natural language search and real-time alerts, let's get LogDNA up and running with Travis. 

<!-- more --> 

## Getting Started 

Let's register an account with LogDNA using the `logdna-cli`, let's first install LogDNA from the CLI: 

```bash
brew install --cask logdna-cli
```

I'm using macOS for this install, now let's signup for an account using the CLI:


```bash
logdna register (your email account) 
```

You'll then set your password and then get a confirmation email. 

## The example use case 

Go the example use case I created [here](https://github.com/Montana/logdna-travis). You'll want to go through some of the files specifically `Gruntfile.js` and `package.json`, and you'll see my current `.travis.yml` looks like this: 

```yaml

   
language: node_js
node_js: "10"
sudo: false
env:
  CXX=g++-4.8
addons:
  apt:
    sources:
    - ubuntu-toolchain-r-test
    packages:
    - g++-4.8
cache:
  directories:
  - node_modules
before_install:
  - npm config set spin false
  - npm install -g npm@^6
  - export DEBUG=logdna*
install:
- npm install
- npm install -g grunt-contrib-copy
- npm install -g grunt-curl
- npm install -g grunt-eslint 
- npm install -g grunt-exec
- npm install -g grunt-line-remover
- npm install -g grunt-mocha-cli
- npm install -g grunt-zip 
- npm install --save-dev load-grunt-tasks
- npm install grunt --save-dev 
script:
- grunt test --force
```
Try and run a build, and if it's successful you should see something like this: 

<img width="1201" alt="Screen Shot 2021-12-31 at 9 43 08 AM" src="https://user-images.githubusercontent.com/20936398/147834381-50b24fbd-6cf4-4fb2-af84-0c799e2bbdea.png">

Remember, this is just a quick example I used, but you can also use LogDNA with your project, I've found it very useful for the notifications. There's various other pluses to add LogDNA to your Travis CI project, and it's simple to integrate. 



