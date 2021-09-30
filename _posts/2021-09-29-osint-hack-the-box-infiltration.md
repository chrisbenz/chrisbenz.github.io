---
layout: post
title: "OSINT Hack the Box - Infiltration"
author: "Chris Benz"
categories: journal
tags: [documentation,sample]
image: 
---

Apart from many of the other challenges on Hack the Box, some of my favorites that I've worked on recently have been from 
Hack the Box's OSINT Challenge category. I'm a big fan of information gathering challenges and find open source intelligence
to be an incredibly interesting topic overall and have found that so far the challenges on Hack the Box do not dissappoint.
The following is a writeup for the Infiltration challenge I recently completed. 

## The Challenge
Released just over two years ago, the Infiltration OSINT challenge reads as follows:
> Can you find something to help you break into the company 'Evil Corp LLC'. Recon social media sites to see if you can find any useful information.

With this out of the way (and appreciating the nice reference to Mr. Robot), it's time to proceed through the challenge.

## Information Gathering

A quick search on `Evil Corp LLC` in DuckDuckGo quickly reveals that this organization at the very least has its own Linkedin page. 

<img src="/assets/img/linkedin-evil-corp.png" alt="A DuckDuckGo search result on Evil Corp LLC displaying the top result, a link to its Linkedin page" width="1000"/>

It's noteworthy that in the description here is a value of text that looks very much like a HTB flag.
<img src="/assets/img/linkedin-evil-corp2.png" alt="The front page of evil corp LLC on Linkedin, featuring a short description, employee count, and buttons for following the compnany on Linkedin or visiting their website." width="1000"/>  


I went ahead and decoded the text of this value. As expected, it's not the flag I'm looking for, but it does appear that I'm on the right track.  
   

<img src="/assets/img/decoded-message.png" alt="The decoded message of the the value which says: You can do this, keep going!!!" width="1000"/>  

Moving along to Evil Corp's posts and other topics, it appears that the organization only has one visible post on their feed. It's just one post, but with
multiple interactions from employees at the company, there may be some extra information to gather here. In particular, these two employees here seem to belong to Evil Corp, so there might be some valuable information on their profiles.  

<img src="/assets/img/linkedin-members.png" alt="The comments of two Evil Corp employees, Alia Mccarty and Abel Bullock" width="1000"/>  

Other than the one interaction on Linkedin, Alia Mccarty's profile had little additional information. However, a quick Google search 
on Mccarty shows that she also appears to have a Twitter profile. She has only a few tweets, but one in particular caught my attention, a tweet
with what appears to be half of a Hack the Box flag. 

<img src="/assets/img/alia-mccarty-twitter.png" alt="A post of Alia Mccarty's with what appears to be half of a HTB flag" width="1000"/> 

I looked around the profile a little more, but couldn't find any other pieces that would connect to this particular piece of text. Since the 
challenge emphasises actually *breaking in* to Evil Corp, I headed back to LinkedIn to look at some more profiles that might have information
which is more consistent with the challenge description.  

From the original post that Evil Corp made on its Linkedin, I was also able to view Abel Bullock's profile, but his profile had little additional
information, and DuckDuckGo and Google searches did not return any other profiles for this particular user.

<img src="/assets/img/abel-bullock-linkedin.png" alt="The front page of Abel Bullock's profile, fairly non-descriptive" width="1000"/>  

With not much else to go on for these users, I returned back to Evil Corp's page to see if there was a way I could discover any new employees of Evil Corp,
as supposedly some 53 users are part of the company, so there may be other profiles to look through.  

Something I find interesting about Linkedin's permissions for viewing profiles is that the ability for a user to view another Linkedin user's profile is largely
based on the vector that one takes in order to view a profile. 
For example, searching for a list of people that are employees of Evil Corp reveals a large list of users that have names ommitted and which are replaced instead
with the text `Linkedin Member`.

<img src="/assets/img/linkedin-members2.png" alt="A list of Linkedin members with most details except for job title ommitted" width="1000"/>  

Yet, if a user is viewing the profile of someone such as an Evil Corp employee like Abel Bullock mentioned earlier, Linkedin will graciously offer the names
of additional profiles that were viewed by other users on Linkedin, some of which appear to be employees of Evil Corp. 

!["Another list of Linkedin members, this time with details included"](/assets/img/linkedin-members3.png)

Notably, Eryn Mcmahon's profile appears to be included in both this list and the other less detailed list of users noted earlier. Like Abel Bullock and 
Alia Mccarty's profiles however, Eryn's profile seemed to also have very little information.  

Interestingly enough however, a DuckDuckGo search revealed that Eryn does have an Instagram profile, so there may be some additional information here to help 
with finding the flag.

<img src="/assets/img/eryn-instagram.png" alt="DuckDuckGo search result showing that Eryn Mcmahon appears to have an Instagram profile" width="1000"/>  

Right away, one post that sticks out to me features a laptop with what appears to be an employee badge which is mostly visible. 

<img src="/assets/img/eryn-instagram2.png" alt="An overview of Eryn Mcmahon's Instagram profile which consists of mostly stock photos" width="1000"/> 

Taking a closer look, it looks like the badge in the photo has Eryn's name, her title at Evil Corp, a barcode, and a long string of text at the bottom which 
appears to be formatted like a HTB flag. 

<img src="/assets/img/eryn-instagram3.png" alt="A picture of one of Eryn Mcmahon's posts" width="1000"/> 

Faint enough as it is, I enlarged this image using Paint and then entered this flag into the challenge submission. Success! Looks like we'll be able to infiltrate Evil Corp. Mr. Robot would be proud. 

## Closing thoughts

Admittedly, I did find this challenge to be fairly simple overall. However, I still encounter situations like this on a regular basis in my own networks.
While not necessarily to the extent of this challenge, I do ocasionally see aquaintances and sometimes even close friends being lackadaisical with
their information when posting to social media. This challenge in particular served as a great reminder that while social media can be an effective tool to share information, we should always aim to be cautious about how much and what type of information we share. Onward to the next challenge!
