* **Description:** Can you find out where the OG meetup point is? The flag is in the format `n00bz{lat,long}` with upto 3 decimal places, rounded. Continue where you left off... Note: Wikipedia can be wrong sometimes ;).
* **Author:** NoobMaster.
## Writeup

Our starting point for this challenge is going to be where we last left on `The Gang 2`, which was @johnhackerdoe's twitter. If we scroll down a little bit on his tweets, we can see that he left a challenge for us  to complete if we want to join his crew. 

![[Pasted image 20240804181528.png]]

From the clues given on the tweets we can get some information:
* Tool: Cyberchef (recommended).
* Algorithm: AES-GCM.
* Ciphertext: 1762841d1888f6b02581990abdf0aaba375c85fd3811a6fb405775fb8d
* Key: "Same as last time" (Unknown).
* IV: "Lat,Long" Up to 3 decimal places. Use the city where we met in 2022 (Unknown).
* Extra Clue: d5e749da6b02c75cb4c763939632503a

After organizing the clues extracted from John's challenge, we need to look for a key that seems to have been used previously and a location where John met someone in 2022. 

The information provided seems vague at the beginning but after thinking a little bit, the `"Same as last time"` made me think that probably a good place to start would be the challenges from previous years to see if maybe the key mentioned could be found somewhere in there.

![[Pasted image 20240804182613.png]]

Visiting n00bzCTF's CTFtime page shows that the event has only been running since 2022, so we don't have to look too far back. Initially i started by checking the 2023 tasks to see if anything related with John Doe would pop up and in fact it does, because we can find an osint challenge called [John Doe Strikes Again](https://ctftime.org/task/25539)

![[Pasted image 20240804182935.png]]

![[Pasted image 20240804183032.png]]

Despite not having a writeup (at least on the CTFTime page, you can find the writeup on [medium](https://medium.com/@khalyylgam/n00bzctf-2023-osint-writeup-2b7cbe4da1c7)), upon reading the description we can see that a secret key was provided, whose value was `YouCanNeverCatchJohnDoe!`. This fits what we are looking for, so for now we are going to continue by checking the 2022 writeups to see if something related to a meeting location can be found.

![[Pasted image 20240804183634.png]]

![[Pasted image 20240804183758.png]]

After checking the 2022 tasks, we find a challenge called [John Doe](https://ctftime.org/task/22110) which involved looking for a city name. Despite again not having any solutions on the CTFTime page, performing a quick google search takes us to a github repository called [n00bzCTF-OfficialWriteups](https://github.com/n00bzUnit3d/n00bzCTF-OfficialWriteups/tree/main). There we can look for the solution of [John Doe](https://ctftime.org/task/22110) which was `Flag - n00bz{46.720_33.154}`, this is could be the coordinates that we were looking for to complete John's challenge.

Now that we have all the missing pieces of the puzzle on John's twitter, we can go back to Cyberchef and stick it all together to see if we can get our flag or if it leads us somewhere else. 

![[Pasted image 20240804184622.png]]

Simply placing the values on the respective fields won't get us anywhere so we need to make sure to properly adjust the data types so the decryption is performed correctly.

![[Pasted image 20240804184741.png]]

So we are finally going somewhere, after encrypting the data we get this url https://discord.gg/9v2FEjndCb. Following it leads us to a group called `"The Hangout"` , lets join and see what else we can get from it.

![[Pasted image 20240804184942.png]]

We've been doing a lot of stuff so lets take a moment to come back to the original question. We need to find the location of the `"OG meetup point"` (Lat,Long). With that clear let's see what we can find on the discord group we just joined.

![[Pasted image 20240804190047.png]]
![[Pasted image 20240804190115.png]]

There is a lot of chatter going on in the group, but the two previous captures have some really good hints towards finding this `"OG meetup point"`. Based on the messages highlighted, John is going to Bengaluru (Bangalore) and he is meeting with some friends near a statue which is about 110 feet tall. That should be good enough to get us somewhere.

![[Pasted image 20240804190441.png]]

![[Pasted image 20240804190722.png]]

If we perform a quick google search for `"Bengaluru 110 feet statue"` , we can find some articles reporting news and find out that the name of this monument is `Nadaprabhu Kempegowda Statue`. Now we can search for it's location on google maps and get the coordinates we were looking for to finally obtain our flag.
## Flag - n00bz{13.199,77.682}