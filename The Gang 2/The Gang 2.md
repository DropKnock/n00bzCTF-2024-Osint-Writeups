* **Description:** You may have gotten your first flag, but it's just the beginning! John Doe, as overconfident as he is, has left you with a riddle. Maybe it hides some secrets? Continue where you left off last time. Flag will already by wrapped in `n00bz{}` 
* **Author:** NoobMaster.
## Writeup

The first indication received on this challenge is to continue where we left off last time, which is [John Doe's profile](https://n00bzunit3d.xyz/authors/johndoe). Here we can see that he has one article published, which is called "[Who Am I?](https://n00bzunit3d.xyz/blog/who-am-i/)".

![[Pasted image 20240804173128.png]]

Upon inspecting the article, we can see that it is some sort of riddle, most likely intended to hide some information that may lead us towards the flag. Another notable thing about this article is the "ChatGPT LOL" at the end.

After reading for a little bit of time and paying attention to the structure of the riddle, we can notice that each sentence starts in upper caps, which isn't out of the ordinary, but could indicate something more. 

If we concatenate every single one of the upper caps letters at the beginning of each sentence, we obtain this interesting message: `"USERNAME IS JOHN HACKER DOE"`.

Ok, so now we have a username to look after, which could lead us into finding the flag we are looking for. In this type of task, i tend to check some of the most popular social media sites (youtube, instagram, facebook, reddit, twitter, etc) and if there is no success, then i usually run tools like [sherlock](https://sherlockproject.xyz/) to find profiles on more obscure social networks.

In this case the username `John Hacker Doe` wasn't that hard to find, because after just a couple minutes i stumbled upon a twitter account created on June with the exact username that we are looking for, and one of it's most recent tweets has the flag we are looking for.

![[Pasted image 20240804173821.png]]
## Flag - n00bz{5t0p_ch4s1ng_m3_4f2d1a7d}
