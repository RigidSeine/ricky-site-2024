---
title: Setting Up a Site Alias for a Github Page
description: Without needing an A record pointing to the Github Pages IP addresses! 
draft: true
---
1. Create a CNAME record in DNS provider
2. Set the custom domain in the Github repo
3. Change baseURL in Hugo config file

Fun fact: In creating this post, I accidentally broke my blog thinking it was a DNS record problem, when in fact I pushed this blog post into the directory containing all my posts (as an intermittent dumping ground) without creating a sub-directory. Lesson learnt.