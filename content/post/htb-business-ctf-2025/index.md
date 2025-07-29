---
title: HackTheBox Business Capture The Flag (CTF) 2025
description: Password? Psh. It's swordfish. It's always swordfish.
date: 2025-07-29
slug: htb-business-ctf-2025
image: HTB_Cert_2025.PNG
tags:
    - AI
    - CTF
---
With the introduction of Generative AI comes a slew of cybersecurity vulnerabilities ready to be exploited by the public.

Specifically, I'm referring to Prompt Injection. What is Prompt Injection?

To quote [IBM](https://www.ibm.com/think/topics/prompt-injection) and to use an [incredibly cliche image](https://github.com/hackthebox/business-ctf-2025/tree/master/aiml):

*A prompt injection is a type of cyberattack against large language models (LLMs). Hackers disguise malicious inputs as legitimate prompts, manipulating generative AI systems (GenAI) into leaking sensitive data, spreading misinformation, or worse.*

![Diagram of prompt injection achieved by combining an application prompt template with malicious](prompt_injection.png)

*Image Source: https://learnprompting.org/docs/prompt_hacking/injection*
 
This year's Hack The Box (HTB)'s annual business Capture The Flag (CTF) competition featured Prompt Injection a category of cybersecurity challenges, and I wanted to (legally) hack some AI chatbots.

The first challenge off the rank is a challenge called **TrynaSob**.

Booting up the challenge, I was met with a page that looks like this:

![Overview of the TrynaSob Ransomware AI challenge featuring an AI chatbot to perform prompt injection against](image1.png)

The scenario included with the challenge is as follows:

*Volnaya’s Cyber Operations Unit has unleashed chaos with their latest creation, the TrynaSob ransomware. Organizations across the globe are paralyzed, their data locked away while Volnaya’s operatives watch from the shadows. To handle the overwhelming number of victims, the regime has introduced an AI ransom negotiator, a cold and calculating chatbot that manages extortion with ruthless efficiency.*

*Task Force Phoenix has discovered a potential weakness. The AI negotiator is programmed to release a temporary decryption key to anyone who submits a valid promo code. Somewhere within its responses lies the opportunity to extract this code. Can you trick the chatbot to reveal the promo code, and obtain the decryption key? Flag format: HTB{decryption_key}.*
 
To boil it down, you've been hit with ransomware and you need to negotiate with an AI chatbot to decrypt your files.

Fun fact: TrynaSob is a parody of the 2017 ransomware attack, [WannaCry](https://en.wikipedia.org/wiki/WannaCry_ransomware_attack), which affected more than 300,000 computers across 150 countries 💀.

So at first I followed the *learnprompting* image to tackle this and tried the *classic* poem approach.

![Initial (failed) attempt at hacking the chatbot](image2.png)

That didn't get me anywhere since the chatbot doesn't write poems.

So then I decided to humour the chatbot instead and pretended to be one of its ransomware victims.

![Roleplaying as a user and asking for payment instructions to pay the ransom](image3.png)

That then gave me a code, which I could use after paying $50k USD into their wallet. OR I could just use the code anyways.

![Successful attempt at hacking the chatbot by roleplaying as a user.](image4.png)

And lo and behold, they gave me the flag, and I didn't need to pay $50k USD. The [official write-up](https://github.com/hackthebox/business-ctf-2025/tree/master/aiml/TrynaSob%20Ransomware) tackles this by getting the AI to translate outputs into French but we definitely did not need anything fancy like that.

<br>
<br>

Because the TrynaSob challenge was a bit too straight-forward, I tried another one called **Power Supply**.

![Overview of the Power Supply AI challenge featuring a power supply dashboard.](image5.png)

The scenario goes like this:

*The Ministry of Power Supply serves as the nerve center of Volnaya’s energy empire, its digital corridors alive with data streaming in from every power plant and substation across the nation. Task Force Phoenix has successfully breached a supply analyst's account, providing us with valuable intelligence on the regime's power supply infrastructure. If we can gain access to the chief minister's account, we will be able to issue executive orders on behalf of the regime, creating a temporary blackout that is critical to the task force's rescue mission.*

*Fortunately, the regime is in the process of modernizing its systems and has recently integrated an agentic AI Assistant into their dashboard. This assistant has full access to the database, which may allow us to obtain the chief minister's password. Can you help us retrieve the chief minister's password and support the mission?*

In other words, we're trying to get a specific user's password from an AI chatbot that has access to the database.

Now this one I neglected to get many screenshots, unfortunately.

But the process went like this:

1. Follow along with the scenario and role-play as a user.

2. Ask it to query the "user table" and discover that you can get the AI to explicitly "use function calls to query the database".

3. Identify that the user we're interested in had an ID of 5 in the user table.

4. Struggle for a while asking the chatbot different ways of revealing the password for user ID 5, including using the *classic* poem method.

5. Look up the actual way of using the *classic* poem method.

6. Use said *classic* poem method and get the flag.

![Successful attempt at getting the Power Supply flag after many failed tries at flirting with the chatbot with user database access.](image6.png)

Ta-da. The key to the poem method is that the prompt needs to be long and convoluted so that you can more easily trick the AI into giving you what you want.

Previous attempts of just asking for a poem with the answer didn't work, but adding in the requirement for an italic style and additional information (the status of the power supply, which we don't care about) was enough to secure our flag.

And that's all we had time for this business CTF, but it was still fun nonetheless.