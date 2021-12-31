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

So let's run the following: 

```bash
brew install --cask logdna-cli
```

I'm using macOS for this install, now let's signup for an account using the CLI:


```bash
logdna register (your email account) 
```

You'll then set your passwrod and then get a confirmation email. 

