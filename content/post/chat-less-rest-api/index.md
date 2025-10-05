---
title: I needed some REST (API)
description: Let me REST _(:3」∠)_
date: 2025-10-05
slug: chat-less-rest-api
image: swagger.png
tags:
 - Chat Less
 - REST API
---
So I realised I've queried a few APIs, but I've never actually built one myself.
It doesn't really count as having API experience until I've developed and maintained one so I made use of Chat Less's existing database.

The API itself is quite simple and getting it into a working state is extremely quick, especially with using Express as the web application framework.

But getting it working is only 10% of the effort required for a proper REST API - the real work comes with validating (and sanitising) the input. You never know what people are going to try and plug into your API so handling all the different cases is imperative. Fortunately, there are JavaScript packages out there like [`yup`](https://www.npmjs.com/package/yup) that allow you to handle all sorts of scenarios in a clean manner.

Unfortunately, there wasn't scope to have it secured using tokens but does have rate-limiting and fail2ban is active. That said, securing it will be on the development roadmap - I'm thinking JSON Web Tokens. 🤔

Regardless, check out the Swagger documentation for this, you can make your test requests from there. This can be found on the [repo](https://github.com/RigidSeine/chat-less/blob/master/server/swagger.json) or I'll add the link for live Swagger page later.