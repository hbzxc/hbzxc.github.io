---
layout: essay
type: essay
title: Why you need to know how to ask a question
# All dates must be YYYY-MM-DD format!
date: 2021-09-08
labels:
  - Need to know
  - how to
---
## Why you need to know how to ask a question

It’s a fact of life that you can’t know everything even though many would claim otherwise. You will need to know how to ask for help. You might think this is simple and it is, don’t be a “loser”. I am referring to the term [Eric Raymond](http://www.catb.org/esr/faqs/smart-questions.html) uses to describe people who waste time asking ambiguous or easily found questions on the internet. The internet is a vast resource, odds are the answer to your question are already out there. Taking the time to look for yourself can often save you time as well as save the time of others who could be answering original questions. Anyone would get annoyed having to answer the same question over and over or have to decipher what a question is asking. If you keep asking annoying questions and people reconize that you will be less likely to get a serious response. As such it is in your best interest to ask a concise and focused question. When you ask the internet for help keep in mind that there is a person on the other side.

## A well asked question:
“When I try to put something in the () brackets of 
  
 ```java
  Friends f = new Friends(friendsName, friendsAge);   
  ```
  it comes up with the error:
  ```
“Constructor Friends in class Friends cannot by applied to given types. Required: no arguments. Found: String, int. Reason: actual or formal argument lists differ in length.”
  ```

But when I take out the arguments my friends list only displays "null 0". Are the values not set even though I have ```String friendsName = input.next();```?
Also, when I try to remove a friend, it doesn't do anything. In the source code it does bring up a warning,
```
  Suspicious call to util.java.Collection.remove: Given object cannot contain given instances of String (expected Friends). 
  ```
I'm confused on what that all means?” 
In addition to this the asker provided the relevant code on stackoverflow in tandem with the question. 
  
Original question: [https://stackoverflow.com/questions/17749409/actual-or-formal-argument-lists-differs-in-length](https://stackoverflow.com/questions/17749409/actual-or-formal-argument-lists-differs-in-length)

This is very direct and focused question. The asker has an idea of why its not working and has made attempts to rectify the issue to no avail. Showing people that you have taken some initiative on your own to answer the question is a good way to have people empathize with you. You don’t just slap it on the counter point and say “fix”.  
It shows in the responses people gave. They were able to pinpoint what the issues was (a missing constructor) . 


## A poorly asked question: 

“I am writing the classic flappy bird game on javascript but for some reason, the space bar activates the game after I click START, and obviously shouldn't do that, should just make the bird jump...for the case I change the key.Code from 32 to 38, which make the bird move when I press the key up, however, the spacebar still starting the game... please check https://github.com/ChrisH30/flappy-bird.git all the code is there.” 
  
Original question: [https://stackoverflow.com/questions/69109867/javascript-spacebar-for-starting-my-code](https://stackoverflow.com/questions/69109867/javascript-spacebar-for-starting-my-code)

From reading the first two replies it can be discerned that people have no idea what this person is going on about. In the response section of the question itself they provide suggestions such as “Please post the relevant code (not the whole application) here, not at a remote site.” and a link “How do I ask a good question?” These responses are a waste of time for both the asker and those responding.
The code is also not posted to the site. There is a lot of extraneous information and the language is imprecise “…when I press the key up, however, the spacebar still starting the game…” which makes it seem like the question was run through google translate. According to the guidelines you should note when your native language is not English. Eventually Chris did get an answer but it did take an hour. It says 34 people viewed it but only one person put in the effort to figure out what this person was asking.


