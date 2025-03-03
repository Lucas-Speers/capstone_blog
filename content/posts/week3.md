+++
date = '2025-03-02'
title = 'Week 3'
weight = 3
+++

# Reflection:

This week I have someone who says they might be my mentor so I am very excited about that.

This week my book has been teaching me about debuggers. The specific debugger it uses, “OllyDbg,” is one that I haven't heard of before and it is very outdated, so it is most likely better to learn a more common debugger in place of OllyDbg. (OllyDbg) Instead, I think I will learn about and how to use WinDbg, a debugger that I have seen recommended for windows debugging. (Marshall and Schultz) I have some experience with GDB from programming C code, but it is built for Linux and could cause problems when running on windows.

# Research:

The idea of a debugger first began to, as the name suggests, be a tool to help programmers debug their code by viewing and changing the state of their program in real time to see what goes wrong. However, people have discovered that it makes a great tool for viewing and changing the state of other programs as well. One common example of using a debugger on someone else's program is Cheat Engine, a tool for hacking games and allowing you to change the state of the game, like setting your health to a ridiculously high number so you are practically invincible. (“Cheat Engine”) The way debuggers work is attaching their program on the other program using Windows’ api. Once attached, it is able to read the program memory and registers as well as change anything about the program. It can also pause the execution of the program as well as deleting threads or changing functions in the program. The debugger can essentially do anything it wants with the program it is debugging. The debugger can also set breakpoints at certain points in the program, which when reached, the program will stop executing. This is useful for running malicious programs so you can set breakpoints before it does anything potentially harmful to allow you to change the state. A debugger is also useful for programs that encrypt or compress their code and decompress it during runtime, something that a plain disassembler is unable to do easily. (Dwivedi and Sikorski)

# Works Cited:

“Cheat Engine.” Www.cheatengine.org, www.cheatengine.org/.

Dwivedi, Ankit. “The Debugger: A Behind-The-Scenes Look at How It Works.” Medium, 2 Sept. 2023, medium.com/@dwivedi.ankit21/the-debugger-a-behind-the-scenes-look-at-how-it-works-983a65883e97.

Marshall, Don, and John Schultz. “WinDbg Overview.” Learn.microsoft.com, 26 Aug. 2024, learn.microsoft.com/en-us/windows-hardware/drivers/debuggercmds/windbg-overview.

OllyDbg. “OllyDbg.” Archive.org, 21 Apr. 2022, web.archive.org/web/20250221231137/www.ollydbg.de/. Accessed 21 Feb. 2025.

Sikorski, Michael, and Andrew Honig. Practical Malware Analysis. San Francisco No Starch Press, 2012.