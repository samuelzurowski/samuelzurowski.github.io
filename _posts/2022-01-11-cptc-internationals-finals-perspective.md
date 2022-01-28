---
title: CPTC Internationals Finals Perspective
tags:
- CPTC
- Penetration-Testing
- Review
date: '2022-01-11 13:40:19'
published: true
---

<p align="center">
  <img src="/images/CPTCLogo_FullColorWithWhiteText.png" alt="GlobalCPTC Logo"/>
</p>

# Introduction

I thought it would be interesting to give my perspective and information that I learned during the International Collegiate Penetration Testing Competition ([CPTC](https://cp.tc/)) Finals as a first time competitor. This is more of the lessons learned rather than the technical details as I feel there is a ton of that out there.

Before I go into details, I would like to thank all the CPTC Team & Volunteers for the amount of effort they placed into making this event possible. All of the competitors apperciate your commitment to creating an environment for us to learn! 

# What is CPTC

CPTC is one of the most unique collegiate cybersecurity competitions that is to train students to be penetration testers through uniquely replicated business environments. Teams of 6 students conduct a penetration test engagement against a fictious company and document findings in a report.  If you are a school considering competiting in this competition we HIGHLY recommend it even if you have no experience in this area. You will learn alot about everything related to penetration testing. CPTC is different from other collegiate competitions such as defending computer networks, searching for flags, or just simply breaking machines. CPTC focuses on replicating the tasks that are performed during a real world penetration test conducted by companies, security firms, and internal security departments.

# This Years Theme

<p align="center">
  <img src="/images//lebon.jpg" alt="GlobalCPTC Theme Logo"/>
</p>

The company Le BonBon Croissant (LBC) is a candy and croissant chain. The company had pressure from a competitor, had a cyber attack, and is based in France. Our team was hired to have a penetration test to ensure the company and customers are protected. 

Within the Request for Proposal (RFP) LBC wanted a firm with expertise and experience in the following:

* Assessments of applications, including internally developed and customized software packages.
* Payment Card Industry Digital Security Standard (PCI-DSS).
* Industrial controls within a storage, delivery, and packaging warehouse facility.
* Payment, transaction, billing, and inventory processing systems.
* Operational processes and technical implementation of customer loyalty and rewards programs.
* Enterprise Resource Planning (ERP) service integration and controls.
* Access management within a embedded industrial systems environment.

# What Makes CPTC Great

As a student, I have had minimal experience related to business interactions or dealing with information related to a business that a penetration tester would need to emphasize. Additionally, if it was not for CPTC, I would not have the writing skills that I currently have. Being able to write a report for a client is crucial for them to understand the problems their corporate networks may have. Some of the things that I defintely learned and improved upon from this competition include:
* Report writing (probably the best skill from this competition I've gained).
* Sensitivity of hosts (e.g. Scanning an PLC may crash it).
* Client interactions & how to properly communicate with them.
* Compliance standards (e.g. PCI DSS).
* Vulnerability scoring (using CVSS).
* Understanding business impact.

As a student I definetly believe that many of these skills are not obtained until you go into industry. While I have taken classes that require some of these they are not to the degree that would be seen in an organization. I think its great that CPTC emphasizes a majority of these skills because it allows students to be introduced to them before going into industry. It really provides the skills ahead of time that students may not have yet.

# Mistakes

One of the parts I like about CPTC is the learning environment created. Being able to make mistakes ahead of time before going into the real world is valuable. During the CPTC Finals I made a stupid mistake that I did not catch until people of the monitoring team came into my room to let us know. It is okay to make mistakes as we are all human and we just need to own up to them. The scope for the first day of the competition was 10.0.17.0/24 but did not include the hosts .50 and .51 because of their sensivitiy. The reason for this is they did not want to cause harm of life or cause hault in their manufacturing operations. For this, I was well aware that these two hosts were not in scope but made a syntax error with nmap that I did not realize:

```bash
nmap 10.0.17.0/24 --exclude 10.0.17.50, 10.0.17.51
```

If you can see the error that happened within this scan its quite simple. Essentially because there is a space after the comma it is treated as a host within the scope (this is because nmap is spaced delimited). This was a simple error and once I came to realization of it I let them know and apologized. When the monitoring team told us this I panicked and said: "It was not us". You should never interact with a client this way. The way I should handle this is:

1. Acknowledge the client of what they said and make it clear you are taking it serious.
2. Let the client know you are going to investigate this.
4. Do an investigation based on the information recieved.
5. Based on your findings discuss what was found.

One thing they told me I did well was that when they came back our team still needed more time. We told them that we needed more time to figure out what happened. Also if you realized that you accidentally attacked out of scope rather than letting the client figure it out, notify them of the mistake. They will really apperciate you if tell them this information and you will gain their trust.

# Report Writing (LaTeX)

One of the things I always hear at CPTC is that you are insane if you use LaTeX for writing your reports. I will agree it is a learning curve however, once you are familar with LaTeX and have a template it is extremely easy to be able to write a report. It is probably easy for my team and I because most of us have written research papers and have used LaTeX for it. One benefit is you don't need to focus on the formatting which probably takes a bunch of time using Microsoft Word (LaTeX automatically does this if prepared ahead of time). Additionally, it is extremely easy to collaborate using LaTeX. This is because of the online platform [overleaf](https://www.overleaf.com) which we used for LaTeX and it is 100% free. All team members can edit the document at the same time which allows our team to save countless time.

Additionally, because I don't see many teams using LaTeX for their report writing I am going to create a post at some point outling how we create ours and post a template on GitHub that we use. Hopefully it will serve to someone as an easy manner to be able to learn LaTeX and potentially use it for CPTC or other purposes. I think it mainly comes down to that I do not want to pay for Microsoft Word! I'll post an announcement on my [twitter](https://twitter.com/_Zen1x) when it comes out.

# Closing Thoughts

This is the last time that I will be competiting in CPTC however, I plan to eventually get involved and volunteer to help them out. The amount of networking, learning, and other opportunities for this competition is amazing. I hope you learned some interesting information about being a penetration tester and can apply it to your jobs and internships. This is my first blog post and I plan to continue to post articles in the forseeable future, please let me know what you think!
