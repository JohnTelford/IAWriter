
# Summary of CDC6600 and 7600

[Summary of CDC6600 and 7600](https://www.perplexity.ai/search/ccf20c62-4c1b-41dc-b5e8-5663262bba0c)

The CDC 6600 and CDC 7600 were early supercomputers designed by Seymour Cray that defined high‑performance computing in the 1960s and early 1970s, with the 7600 roughly quintuple the performance of the 6600 in many workloads. Both used 60‑bit words and a central scientific processor supported by multiple peripheral processors, but the 7600 added much higher clock speed and deeper pipelining.​

## CDC 6600 Overview
Introduced in 1964, the CDC 6600 is widely regarded as the first successful supercomputer, delivering up to about 3 megaFLOPS and outperforming the IBM Stretch by roughly a factor of three.​

It used a 60‑bit word, ones‑complement arithmetic, and an 18‑bit addressing scheme, with a central processor running at about 10 MHz and directly accessing up to roughly 960 KB of core memory.​

The machine’s architecture was “distributed”: one central scientific processor handled computation while ten 12‑bit peripheral processors performed operating system and I/O tasks in a barrel‑processor arrangement, allowing overlap of computation and I/O.​

The 6600 employed multiple functional units and a scoreboard mechanism to overlap instruction execution without out‑of‑order hardware, making it a precursor to later RISC and superscalar ideas.​

## CDC 7600 Overview

The CDC 7600, introduced later in the 1960s, was designed as the successor to the 6600 and became the world’s fastest computer, typically running around five times faster than the 6600 on many applications.​

It kept the 60‑bit word and general programming model but raised the clock to about 36 MHz (27.5 ns cycle), reaching around 15 MIPS and roughly 36 megaFLOPS peak, with 65K 60‑bit words of primary (small core) memory and up to 512K words of secondary (large core) memory.​

The 7600 pushed pipelining much further, with multiple floating‑point units and carefully staged memory access, and used a distinctive C‑shaped physical layout to minimize signal path lengths and improve speed.​

Architecture and design themes
Both systems used 60‑bit word length, ones‑complement integers, and core memory, and both relied on a central processor plus a set of peripheral processors handling I/O and operating system functions.​

The 6600 organized memory as a single banked core store, while the 7600 introduced a two‑level core memory (small and large core) with pipelined transfers and higher bandwidth, effectively acting like an early main‑memory hierarchy.​

Instruction sets were relatively streamlined compared to contemporary mainframes, and heavy use of functional‑unit overlap and score boarding in the 6600, then extensive pipelining in the 7600, gave them characteristics that later commentators have likened to early RISC designs.

## Historical Impact

From 1964 to 1969, the CDC 6600 held the title of the world’s fastest computer, until the 7600 displaced it, and both were widely used in scientific and engineering computing, including weather modeling and physics research.​

These machines cemented Seymour Cray’s reputation and shaped subsequent supercomputer designs, influencing later CDC Cyber systems and the Cray‑1, especially in their emphasis on high clock rates, parallel functional units, and streamlined instruction execution.




# Early Super Computers

I operated and programming these early supercomputers from Control Data Corporation, specifically the CDC-6600 and 7600.



### [Summary](https://ed-thelen.org/comp-hist/vs-cdc-6600.html)

[Comparison 6600 7600](#)

## The Control Data 6600
Reference: [DESIGN OF A COMPUTER. THE CONTROL DATA 6600 ]](https://www.perplexity.ai/search/3995c0cc-d38b-49a6-bcf0-274350fefc97)






Seymour Cray, renowned for his groundbreaking work at Control Data Corporation, revolutionized high-performance computing with his innovations in architecture. His pioneering concepts, including instruction pipelining, parallel execution, and the utilization of multiple peripheral processors, laid the foundation for the modern computing landscape. The CDC 6600, introduced in 1964, stands as a testament to Cray’s genius, widely regarded as the world’s first supercomputer. It boasted an astonishing speed, executing up to 3 million instructions per second, nearly ten times faster than any prior computer. Cray’s simplified and efficient designs not only pushed the boundaries of computing but also anticipated the concepts that would later become integral to today’s RISC processors.




### Architectural Innovations
> Cray focused on minimizing component size and wiring length, reducing signal delays and allowing for faster clock speeds (the CPU operated at 10 MHz, far beyond most contemporaries).​
> 
> He devised a simplified central processor built for rapid logic and arithmetic, placing it at the heart of the machine's cross-shaped chassis, surrounded by circuit boards compactly arranged to maximize speed and minimize interference.​
> 
> The 6600 featured ten peripheral processors dedicated to I/O and housekeeping, letting the central processor focus exclusively on computations—a revolutionary design that foreshadowed modern multiprocessing and parallel architectures.​

### Component and Cooling Engineering
> Cray exploited the emerging technology of silicon transistors (much faster than previous germanium types), allowing the CPU to execute instructions in fewer cycles at higher speeds.​
> 
> He innovated assembly methods, using "cordwood" module construction to densely pack circuitry and keep wiring short, further boosting performance.​
> 
> Cray developed a robust cooling system using Freon (and in later designs, liquid nitrogen) for the modules, reducing thermal noise and ensuring reliability at high speeds.​
> 
### Design Philosophy and Team
> Cray insisted on quiet, small teams, moving his lab to Chippewa Falls, Wisconsin for minimal management interference and maximal engineering focus.​
> 
> With a team of just 14 engineers and 4 programmers, Cray emphasized elegant simplicity, cutting instruction sets to essentials and maximizing throughput.​
> 
> The 6600's custom operator console replaced hundreds of switches and lights with screens and keyboards—an interface leap for the era.​
> 
### Legacy
> The CDC 6600’s architecture enabled major advances in scientific computing (simulating weather, nuclear reactions, and more) and sold over 100 units worldwide.​
> 
> Cray’s methods—parallel processing, simplified instruction sets, extreme physical and electrical efficiency—set foundations for future supercomputers and inspired industry rivals.​
> 
> Cray's meticulous focus on speed, simplicity, and parallelism—while leveraging groundbreaking transistor and cooling technology—made the CDC 6600 a quantum leap for computing performance.

### Cpu
“In the 6600 Computer, perhaps even more than in any previous computer, the control system is the difference. The essential premise of the Central Processor is "functional parallelism." Chapter V has dealt with the functional units. This chapter will show the methods employed to control these units in parallel.
It is well to repeat the essentials of the "functional parallelism" of the
6600 Computer. These are:
• Separate functional units,
• Registers for operands, indexes, and addresses,
• Instruction Stack,
• Reservation control, or Scoreboard.
This last is the major part of the control system. There are, of course,
other elements of the control system are also essential. For example,
the operating system for the 6600 provides overall control of job scheduling,
allocation of CPU and storage, and the control of Input and Output.”


### Scoreboard
“A unique and essential part of the 6600 Central Processor control is the
Unit and Register Reservation Control, or the Scoreboard. What is intended by this design is the simultaneous operation of functional units on a single instruction stream. Many operations in these units are quite independent of others, due to the relative simplicity of the instructions. It is often particularly apparent that a sequence of arithmetic or logical operations can be executed simultaneously with a sequence of control or house-keeping operations. Again, examples will be shown in which considerable overlap is possible even in the single sequence.
One major premise of the Scoreboard design is that each new instruction be issued to its functional unit as early as possible to allow flowing instructions to be issued. In some cases, an issued instruction may be held up after issue awaiting input operands, while a following instruction may proceed without restraint.”

### Peripheral Processors
The processing requirements in an input-output section of any computer include the following.
- Transferring data between peripheral device and central storage.
- Controlling the initiation of peripheral device actions.
- Establishing priorities between devices.
- Buffering data between asynchronous devices.
- Interrupting the central processor for execution of priority tasks.
This list is not exhaustive but illustrates the nature of the processing assigned to the ten small processors in the 6600 Computer.
These Peripheral and Control Processors, or PPU’s, are constructed within the main frame cabinet of the 6600. This provides convenient use of identical logic and storage modules as in the central processor and central storage, plus the shared use of the power and cooling system. It also allows a unique form of design, called the “barrel.”

### Dead Start
A typical obstacle to the understanding of a complex instrument is the inability to discover the answer to the question, “How does it start?” This section is devoted to answering that question.
A first assumption is made that there are  peripheral devices capable of loading the computer’s operating system. These may be:
Magnetic tape
Punched cards
Magnetic disk.

A second assumption is made that a direct entry of “machine language” programs is possible from these devices. To activate the DEAD START sequence, the 6600 cabinet contains a panel containing several control switches and a 12 by 12 matrix of switches.

![](Dead%20Start.png)
Dead Start Panel

[Table of Contents](#)
---- 

## The Control Data 7600

The CDC 7600, a landmark supercomputer designed by Seymour Cray for Control Data Corporation, was introduced in 1969. It held the title of the world’s fastest computer for most of the 1970s. The CDC 7600 succeeded the CDC 6600, maintaining code compatibility while significantly enhancing its performance. It is renowned for its groundbreaking hardware engineering and its profound influence on the design principles of subsequent CPUs.  
  
Key technical features include:
> 
> Performance: Achieved speeds exceeding 10 MIPS (millions of instructions per second), with floating-point throughput up to 40 megaflops. It typically ran five times faster than the CDC 6600.
> 
> Memory: Utilized a small-core memory of 65,536 60-bit words with a 27-nanosecond clock cycle.
> 
> Architecture: Streamlined instruction issue logic compared to the CDC 6600, enabling one instruction per cycle pipelined, in-order execution without the complex scoreboard out-of-order logic of its predecessor.
> 
> Hardware: Used high-speed discrete transistors in multi-board modules at a time when competitors were switching to integrated circuits.
> Design: Its large, U-shaped chassis provided efficient cooling and minimized wire lengths for reliability and speed.


_[Table of Contents](#)





