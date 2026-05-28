---
title: Server Migration with Ansible
description: "Like shifting houses. *Alt-text: It's an image of bindle with a server inside it.*"
date: 2026-05-28
image: server-migration-bindle.png
tags:
  - Ansible
  - IaC
links:
  - title: GitHub
    description: A link to the Github repo with the Ansible playbook that I used for server migration.
    website: https://github.com/RigidSeine/ansible-server-setup-example
    image: https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png
---

A milestone in a series of migrations that I'm doing, but also a first foray into using Ansible!

I gotta say, this Ansible stuff is pretty neat - especially if you make the most of the **idempotent** nature of the technology.

What the heck is an idempotent, you may ask? It's when you apply an operation multiple times without chaning the result. The simplest way to demonstrate it is with a little bit of maths.

- If you multiply any number with 0, you'll get 0.
- If you multiply any number with 1, you'll get that number again.

And if you repeat these operations, you get the same result every time.\
Hence, these operations are idempotent.

In the context of Ansible, the idea for your script is supply the state you want your component to be in so that when you re-run the script, you'll either return to the state or nothing will change.

So I've gone ahead and created an Ansible playbook for the purpose of being able to move my server between cloud providers easily. In this case, I ditched Microsoft Azure for Akamai Linode with the idea of doing some cost-saving.

As part of this, I did also move Tenkiame to a docker container beforehand to really boost portability of my setup.

And since I figured my colleagues might have an interest in this, I also published an anonymised version of the repo I'm using.