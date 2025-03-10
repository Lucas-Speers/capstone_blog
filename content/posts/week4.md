+++
date = '2025-03-09'
title = 'Week 4'
weight = 4
+++

# Reflection:

This week I really wanted to use my knowledge of malware and actually build my own malware. I wanted to build an executable program that will search for another program running on the machine and inject a payload directly into the memory of the program. The end result was a modified version of the program shown in “Basic Process Injection with C.” (Lsec) It works by iterating over every running process and getting the process ID for the first one that matches the executable we want to attack, like “firefox.exe” because of its access to the network that is crucial for calling back to our server. Once the process is found, it uses some windows functions to allocate and write to some memory  in the firefox process. The final step is to run a new thread in firefox that uses the memory as executable code. The payload we inject can be easily made using the MetaSploit Framework, specifically, the msfvenom command. I did have a lot of problems implementing this malware. First of all, some of the functions I used returned differently formatted text. This was an issue because I had to compare the desired executable name to each one of the processes, which was returning false every time due to the formatting. Once this was fixed, I had another problem, Windows Defender would identify my program as malicious and delete it. It was recognizing my payload as malware and deleting the entire program because of it. The solution was to repeatedly encode the payload until it wasn’t recognised. This is the equivalent of putting it in a zip file in a zip file in a zip file and so on. It is concerning how easily it caused Windows Defender to no longer recognize it and allow it to be run. The last problem, however, has stumped me. Everything works just fine until I try to run the payload through a new thread in the program, where it suddenly crashes the target program. There are no logs produced by the program that would suggest that it crashed unexpectedly, it just closes.

# Research:

This week, I learned all about the behavior of malware. Not all malware is made the same and can all function very differently, but they can be categorized by the techniques they use. The first is downloaders and launchers, tiny programs that download the actual malware and run it. The first advantage is that they can be very small due to the fact that they do not contain the payload, making them fast to download. The second is that if the hacker knows that their malware is under investigation, they can pull the plug on their server and the person trying to disassemble the malware will be unable to due to them not being able to download it. (Sikorski and Honig)

Another category of malware is the backdoor. Backdoors work by purposefully adding a vulnerability in the target machine that can be exploited by the hacker. Backdoors can be in all shapes and sizes, even being built into popular software that users install. Backdoors can even be built into hardware which can be undiscovered for longer and be almost impossible to remove when found. (Sikorski and Honig)

Another category of malware is a rootkit. A rootkit is a way of obscuring that there even is malware on the computer in the first place. It obscures itself by hooking Windows’ calls for certain actions like terminating a program, and running malicious code like ignoring the call if it is trying to terminate the malware. Or hooking calls to reading files to not show that the malware doesn’t even exist in the files. This can make it impossible to detect or remove malware by common methods. (Sikorski and Honig)

# Works Cited:

Lsec. “Basic Process Injection with c - Lsec - Medium.” Medium, 25 Apr. 2024, medium.com/@lsecqt/basic-process-injection-with-c-e6d4d2fa3b4a.

Sikorski, Michael, and Andrew Honig. Practical Malware Analysis. San Francisco No Starch Press, 2012.