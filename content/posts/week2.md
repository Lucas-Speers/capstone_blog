+++
date = '2025-02-23'
title = 'Week 2'
weight = 2
+++

# Reflection:

I have continued reading “Practical Malware Analysis” and have started the hands-on practice that the book provides, which I was very excited to start working on. The book provides a lot of example programs to pick apart with the newfound knowledge it teaches in each chapter. It was quite difficult to figure out how to download and use these code segments because Windows Defender was (rightfully) detecting multiple pieces of malware when downloading the zip file with all the samples for the labs in the book. Every time I downloaded the zip file, it would get deleted by Windows and gave about 20 “high security risks.” I fixed this by allowing each individual file in Windows Defender and temporarily disabling the real-time protection when I open the files with a disassembler.

This week I had to choose between two disassemblers that I could use, Ida and Ghidra. Ida is the program that the book I’m reading uses, although to use it at its full potential, it is a paid software. Ghidra is a free software made by the NSA that I want to use in the future, but the book does not focus on this software. I have ultimately decided to use Ida and carry over my knowledge of reverse engineering to Ghidra once I am done with the book. (Cortuk)

# Research:

This week I learned about assembly instructions. Assembly instructions are near 1-to-1 placeholders for actual instructions read by the computer, but assembly assigns simple names to the instructions. This allows you to represent the cpu instruction of “B9 42 00 00 00” as “mov ecx, 0x42” which can be read as “move the value of 0x42 into the ecx register.” Many instructions are self explanatory, but some like “jecxz” need to be memorized by the programmer. Many assembly instructions will also set flags, or indicators of how the instruction worked. For example, the “cmp” instruction will take two values and compare them and set the “ZF” flag if the two values are equal. Other instructions can use these flags to change their behavior like the “jz” instruction, which will jump to a different location in memory if the “ZF” flag is set. There are also “registers” that you need to know for assembly. Registers are storage that can be accessed very quickly by the CPU, even faster than RAM. It is also important to know which instructions affect which registers and how. (Cloutier and Sikorski)

This week I also learned some disassembly with a tool called “Ida.” Ida is a powerful tool that can take an .exe or .dll file and scan the file through all the code and give the assembly instructions that make up each function. It also has many built-in features like the strings tool that make Ida an all-in-one tool for reverse engineering. With this tool, I was able to learn about the layout of assembly that you find in your average program. Ida makes reading assembly very easy with its graphical view of the flow of a program. For an instruction like the previously mentioned “jz” instruction, the graph will split into two paths to each possible location in the program that the program counter will go to next.

Ida is also designed to be an interactive software. To explain, the disassembled code that Ida produces is filled with hundreds of functions and variables with no names. This makes it extremely difficult to figure out what basically anything does in the program at a glance. However, through a lot of hard work, someone can look at the behavior of smaller functions and label them appropriately. For example, if an unnamed function only calls functions relating to getting the system language, you can rename the function to “get_language” and find all the places that it is referenced to see the new name instead of a default name like “func_100486f” that Ida puts in. After doing this process repeatedly, you can make the assembly more readable and easily understand what is happening in any given function, and hopefully, the entire program. (Baggs; Sikorski)

# Works Cited:

Baggs, Nathan. “Every Game I Hacked in 2024.” YouTube, 13 Dec. 2024, www.youtube.com/watch?v=ncc4UMbu_T0. Accessed 16 Feb. 2025.

Cloutier, Felix. “X86 and Amd64 Instruction Reference.” Www.felixcloutier.com, 18 Feb. 2024, www.felixcloutier.com/x86/.

Cortuk, Derya. “Reverse Engineering Tools - Derya Cortuk - Medium.” Medium, Medium, 13 Jan. 2024, medium.com/@derya.cortuk/reverse-engineering-tools-fccc151f0a82.

Sikorski, Michael, and Andrew Honig. Practical Malware Analysis. San Francisco No Starch Press, 2012.