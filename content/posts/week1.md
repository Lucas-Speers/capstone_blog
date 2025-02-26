+++
date = '2025-02-16'
title = 'Week 1'
weight = 1
+++

# Reflection:

This week I started on my book, “Practical Malware Analysis,” a book about taking apart malware to find out how they work, a process called reverse engineering. The book takes a focus on malware as malware programs are actually very small and therefore can be very easy to reverse engineer. Another reason malware is a good starting point is that many malwares will obfuscate their code, making it harder to reverse engineer. Being able to identify and handle obfuscated code is very important and a useful skill to learn. Lastly, as a potential cyber security specialist, it may be my job to reverse engineer a virus in order to understand the scope of the attack, as well as how to stop and remediate the attack.

The reason I chose this book is because I am familiar with the publisher, “No Starch Press,” and have enjoyed the style of learning the books provide. I am glad to say “Practical Malware Analysis” is no different than what I am used to from the publishers other books.

In addition to the book, I have watched some videos on Nathan Baggs' journey in reverse engineering many old and new games to get them to run. Unfortunately, while the content is entertaining and I have learned some high-level concepts, I lack the fundamental knowledge at the moment to fully understand and learn from the material. Once I am further into this project, I hope to revisit the material and possibly follow along to learn new tricks and strengthen my skills.

# Research:

My research this week is from my book, focusing on my first question on reverse engineering: “Where do I even start?” The answer to this is “Basic static analysis,” which refers to the data that you can gain through simple analysis of the malware without running it or decompiling it. (Sikorski) Only a little information can be gained, but it can be extremely useful for getting an idea of what the malware may or may not be doing.

The best first step for basic static analysis is to use the “string” program. It will look through the executable for any ascii words or sentences found in the file. This can be very useful if you find a string like “10.64.20.43” because you have just found an IP address that the program uses. It can also be used to determine functionality if you find a string like “Mail system DLL is invalid.!Send Mail failed to send message.” because that will immediately tell you that this malware likely sends emails as a part of its attack. (Sikorski)

The next best way to gather information on an executable, is to look at linked libraries. When functions are compiled, much of the code will be the same across each program. Having every program have the code to open a window can be very inefficient, so instead, there exist files that have common functions that programmers can use. When an executable that uses one of these files is run, the program needs to tell Windows which libraries to load. Determining the libraries that are loaded can help determine what the executable might do. (Sikorski)

# Works Cited:

Baggs, Nathan. “Every Game I Hacked in 2024.” YouTube, 13 Dec. 2024, www.youtube.com/watch?v=ncc4UMbu_T0. Accessed 16 Feb. 2025.

Sikorski, Michael, and Andrew Honig. Practical Malware Analysis. San Francisco No Starch Press, 2012.