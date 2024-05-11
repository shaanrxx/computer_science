# Register
Registers are small, fast storage units within a computer's CPU that temporarily hold data and instructions during processing, enabling quick access and manipulation of information.
Internally, A register is a collection of flip flop (A flip flop is basically a storage device capable of storing 1 bit of information). Hence a register is able to store
multiple bits of information. It is a very cruicial and important part of a computer. Even a very basic computer has atleast eight major reigsters.

These eight major registers are:
| Register Name             |Bits|              Function                            |
| :-----------------------: |:--:| :-------------------------------------:          |
|  Data register (DR)       | 16 |   Holds memory Operand                           |
| Address Register (AR)     | 12 | Holds address for memory                         |
|   Accumulator(AC)         | 16 | Processor Register used to arithmetic and logic  |
| Instruction Register (IR) | 16 | Holds the instruction code                       |
| Programme Counter (PC)    | 12 | Holds the address of the next instruction        |
| Temporary Register (TR)   | 16 | Holds the temporary data                         | 
| Input Register (INPR)     | 8  | Holds the input character                        |
| Output Register (OUTR)    | 8  | Holds the output character                       | 

The above values are for a 16 bit machine.
These basic computer registers are connected by a common bus through which information is transferred among these registers and operations are performed.

If we talk about basic operations, then any basic register is capable of four operations:

1. Load - In this operation a value is loaded into the flip flops of the register.
2. Increment - In this operation the register functions as a counter and increments the data stored in it.
3. Clear - In this operation the registers clears the data in its flip flops i.e. whichever flip flop in the register has a state of 1 (High) is made 0 (low)
4. Shift - A register is capable of shifting the values in the flip flop leading to left shift(multiply by 2) or right shift(divide by 2) operations.

# Special Purpose Register
Special types of register such as: the status register, control register, and floating-point control registers, are special components of CPU architecture. They facilitate essential functions such as managing arithmetic operation outcomes, controlling CPU behavior and configuration, and handling floating-point arithmetic operations. These registers play vital roles in ensuring efficient, reliable, and versatile operation of modern CPUs across various computing tasks and environments. 

# Status Register (Flag Register): 
Holds individual flags indicating various conditions or outcomes of arithmetic and logic operations. Some common flags found in the status register include:

Zero Flag (Z): This flag is set if the result of an arithmetic or logic operation is zero.
Carry Flag (C): The carry flag is set if an arithmetic operation generates a carry out of the most significant bit or a borrow from the least significant bit.
Sign Flag (S): The sign flag reflects the sign of the result of an arithmetic operation. It is set if the result is negative (i.e., the most significant bit is 1).
Overflow Flag (V): The overflow flag indicates whether an arithmetic operation resulted in an overflow, typically in signed arithmetic, where the result exceeds the representable range of the data type.
Parity Flag (P): In some architectures, the parity flag indicates whether the number of set bits in the result is even or odd.
Direction Flag (D): The direction flag controls the direction of string instructions, specifying whether they auto-increment or auto-decrement the memory address.

# Control Register: 
Used to control certain aspects of CPU operation and configuration. They may include registers such as:

Program Status Word (PSW): The PSW is a control register that contains status bits and control bits that influence the behavior of the CPU, such as interrupt enable/disable flags, privilege level bits, and mode bits indicating the current CPU mode (e.g., user mode, kernel mode).
Interrupt Mask Register (IMR): The IMR is used to mask or enable specific interrupt sources, allowing the CPU to prioritize interrupts and handle them appropriately.
Timer Control Register: This register controls the behavior of system timers, such as setting timer intervals, enabling timer interrupts, and configuring timer modes.
Memory Protection Registers: These registers define memory protection settings, such as read/write permissions, access control lists, and memory segmentation parameters, to enforce memory protection and security policies.

# Floating-Point Control Registers: 
In CPUs with floating-point units (FPUs) for performing floating-point arithmetic operations, floating-point control registers are used to control FPU operation, precision, rounding modes, and exception handling.

# Cache
A cache -- pronounced CASH -- is hardware or software that is used to store something, usually data, temporarily in a computing environment.

It is a small amount of faster, more expensive memory used to improve the performance of recently or frequently accessed data. Cached data is stored temporarily in an accessible storage media that's local to the cache client and separate from the main storage. Cache is commonly used by the central processing unit (CPU), applications, web browsers and operating systems.

Cache is used because bulk or main storage can't keep up with the demands of clients. Cache decreases data access times, reduces latency and improves input/output (I/O). Because almost all application workloads depend on I/O operations, the caching process improves application performance.


## How does a cache work?
When a cache client attempts to access data, it first checks the cache. If the data is found there, that is referred to as a cache hit. The percent of attempts that result in a cache hit is called the cache hit rate or ratio.

Requested data that isn't found in the cache -- referred to as a cache miss -- is pulled from main memory and copied into the cache. How this is done, and what data is ejected from the cache to make room for the new data, depends on the caching algorithm, cache protocols and system policies being used.


## Cache associated with CPU
Data in primary memory can be accessed faster than secondary memory but still, access times of primary memory are generally in a few microseconds, whereas the CPU is capable of performing operations in nanoseconds. Due to the time lag between accessing data and acting on data performance of the system decreases as the CPU is not utilized properly, it may remain idle for some time. In order to minimize this time gap new segment of memory is Introduced known as Cache Memory.



### Benefits
1. **Faster access**: Faster than main memory. It resides closer to CPU , typically on same chip or in close proximity. Cache stores subset of data and instruction.
2. **Reducing memory latency**: Memory access latency refers to time taken for processes to retrieve data from memory. Caches are designed to exploit principle of locality.
3. **Lowering bus traffic**: Accessing data from main memory involves transferring it over system bus. Bus is shared resource and excessive traffic can lead to congestion and slower data transfers. By utilizing cache memory , processor can reduce frequency of accessing main memory resulting in less bus traffic and improves system efficiency.
4. **Increasing effective CPU utilization**: Cache memory allows CPU to operate at a higher effective speed. CPU can spend more time executing instruction rather than waiting for memory access. This leads to better utilization of CPU’s processing capabilities and higher overall system performance.
5. **Enhancing system scalability**: Cache memory helps improve system scalability by reducing impact of memory latency on overall system performance.

### Types of cache
Within a CPU, there are usually multiple levels of cache organized in a hierarchy, each offering different characteristics in terms of size, latency, and proximity to the CPU cores. 

**L1 or Level 1 Cache**: It is the first level of cache memory that is present inside the processor. It is present in a small amount inside every core of the processor separately. The size of this memory ranges from 2KB to 64 KB.

**L2 or Level 2 Cache**: It is the second level of cache memory that may present inside or outside the CPU. If not present inside the core, It can be shared between two cores depending upon the architecture and is connected to a processor with the high-speed bus. The size of memory ranges from 256 KB to 512 KB.

**L3 or Level 3 Cache**: It is the third level of cache memory that is present outside the CPU and is shared by all the cores of the CPU. Some high processors may have this cache. This cache is used to increase the performance of the L2 and L1 cache. The size of this memory ranges from 1 MB to 8MB.

# Cache Coherency:
In multi-core processors where multiple cores share the same L3 cache, maintaining cache coherency becomes essential to ensure data consistency across cores. Cache coherency protocols, such as MESI (Modified, Exclusive, Shared, Invalid), are use to manage data coherence and synchronization between caches, minimizing data inconsistencies and ensuring correct program execution.


# RAM
RAM (Random Access Memory) is the hardware in a computing device where the operating system (OS), application programs and data in current use are kept so they can be quickly reached by the device's processor. RAM is the main memory in a computer. It is much faster to read from and write to than other kinds of storage, such as a hard disk drive (HDD), solid-state drive (SSD) or optical drive.

Random Access Memory is volatile. That means data is retained in RAM as long as the computer is on, but it is lost when the computer is turned off. When the computer is rebooted, the OS and other files are reloaded into RAM, usually from an HDD or SSD.

## Function of RAM
Because of its volatility, RAM can't store permanent data. RAM can be compared to a person's short-term memory, and a hard disk drive to a person's long-term memory. Short-term memory is focused on immediate work, but it can only keep a limited number of facts in view at any one time. When a person's short-term memory fills up, it can be refreshed with facts stored in the brain's long-term memory.

A computer also works this way. If RAM fills up, the computer's processor must repeatedly go to the hard disk to overlay the old data in RAM with new data. This process slows the computer's operation.

A computer's hard disk can become completely full of data and unable to take any more, but RAM won't run out of memory. However, the combination of RAM and storage memory can be completely used up.

## How does RAM work?
The term random access as applied to RAM comes from the fact that any storage location, also known as any memory address, can be accessed directly. Originally, the term Random Access Memory was used to distinguish regular core memory from offline memory.

Offline memory typically referred to magnetic tape from which a specific piece of data could only be accessed by locating the address sequentially, starting at the beginning of the tape. RAM is organized and controlled in a way that enables data to be stored and retrieved directly to and from specific locations.

Other types of storage -- such as the hard drive and CD-ROM-- are also accessed directly or randomly, but the term random access isn't used to describe these other types of storage.

RAM is similar in concept to a set of boxes in which each box can hold a 0 or a 1. Each box has a unique address that is found by counting across the columns and down the rows. A set of RAM boxes is called an array, and each box is known as a cell.

To find a specific cell, the RAM controller sends the column and row address down a thin electrical line etched into the chip. Each row and column in a RAM array has its own address line. Any data that's read flows back on a separate data line.

RAM is physically small and stored in microchips. It's also small in terms of the amount of data it can hold. A typical laptop computer may come with 8 gigabytes of RAM, while a hard disk can hold 10 terabytes.

A hard drive, on the other hand, stores data on the magnetized surface of what looks like a vinyl record. Alternatively, an SSD stores data in memory chips that, unlike RAM, are nonvolatile. They don't depend on having constant power and won't lose data once the power is turned off. RAM microchips are gathered together into memory modules. These plug into slots in a computer's motherboard. A bus, or a set of electrical paths, is used to connect the motherboard slots to the processor.

Most PCs enable users to add RAM modules up to a certain limit. Having more RAM in a computer cuts down on the number of times the processor must read data from the hard disk, an operation that takes longer than reading data from RAM. RAM access time is in nanoseconds, while storage memory access time is in milliseconds.

## How much RAM do you need?
The amount of RAM needed all depends on what the user is doing. When video editing, for example, it's recommended that a system have at least 16 GB RAM, though more is desirable. For photo editing using Photoshop, Adobe recommends a system have at least 3GB of RAM to run Photoshop CC on a Mac. However, if the user is working with other applications at the same time, even 8GB of RAM can slow things down.


## Types of RAM
**Dynamic Random Access Memory (DRAM)** makes up the typical computing device's RAM, and as was previously noted, it needs that power to be on to retain stored data.
Each DRAM cell has a charge or lack of charge held in an electrical capacitor. This data must be constantly refreshed with an electronic charge every few milliseconds to compensate for leaks from the capacitator. A transistor serves as a gate, determining whether a capacitor's value can be read or written.

**Static Random Access Memory (SRAM)** also needs constant power to hold on to data, but it doesn't need to be continually refreshed the way DRAM does.
In SRAM, instead of a capacitor holding the charge, the transistor acts as a switch, with one position serving as 1 and the other position as 0. Static RAM requires several transistors to retain one bit of data compared to dynamic RAM which needs only one transistor per bit. As a result, SRAM chips are much larger and more expensive than an equivalent amount of DRAM.

However, SRAM is significantly faster and uses less power than DRAM. The price and speed differences mean static RAM is mainly used in small amounts as cache memory inside a computer's processor.


## Computer Storage
Computers need some form of non-volatile storage—a place where data can stay even when the computer is turned off, so you don’t have to reload and re-enter everything each time you use the computer. That’s the point of having storage in addition to RAM.

Storage for the vast majority of computers in use today consists of a drive, either an HDD or an SSD. Drives can provide a lot of space that can be used to store applications, documents, data, and all the other stuff you need to get your work done (and your computer needs to operate)


## Difference Between Memory and Storage
Your computer’s main memory is called RAM (i.e., random access memory). You can think of it as a workspace the computer uses to get work done—a desk, if you will. When you double-click on an app, open a document, or do much of anything, part of your “desk” is covered and can’t be used by anything else. As you open more files, it is like covering your desk with more and more items. Using a desk with a handful of files is easy, but a desk that is covered with a bunch of stuff gets difficult to use.

In addition to RAM, your computer probably also has storage like a hard disk drive (HDD) or solid-state drive (SSD) where data is recorded for the long term. You could use it to store old company records like a tax return from five years ago, your music collection, and apps that you use. Computer storage is like a filing cabinet—a place next to your workspace where you can retrieve information as needed.

RAM is volatile, meaning the information that’s put in there disappears when the power is turned off or when the computer is reset. Storage is different—it’s persistent. Data stays written on the disk until it’s erased or until the storage medium fails (more on that later).

## History of RAM: RAM vs. SDRAM
RAM was originally asynchronous because the RAM microchips had a different clock speed than the computer's processor. This was a problem as processors became more powerful and RAM couldn't keep up with the processor's requests for data.

In the early 1990s, clock speeds were synchronized with the introduction of synchronous dynamic RAM, or SDRAM. By synchronizing a computer's memory with the inputs from the processor, computers were able to execute tasks faster.

However, the original single data rate SDRAM (SDR SDRAM) reached its limit quickly. Around the year 2000, double data rate synchronous Random Access Memory (DDR SRAM) was developed. This moved data twice in a single clock cycle, at the start and the end.

DDR SDRAM has evolved three times, with DDR2, DDR3 and DDR4, and each iteration has brought improved data throughput speeds and reduced power use. However, each DDR version has been incompatible with earlier ones because, with each iteration, data is handled in larger batches.

DDR3 vs. DDR2 vs. DDR
Image Needed

## GDDR SDRAM
Graphics double data rate (GDDR) SDRAM is used in graphics and video cards. Like DDR SDRAM, the technology enables data to be moved at various points in a CPU clock cycle. However, it runs at higher voltages and has less strict timing than DDR SDRAM.

With parallel tasks, such as 2D and 3D video rendering, tight access times aren't as necessary, and GDDR can enable the higher speeds and memory bandwidth needed for GPU performance.

Similar to DDR, GDDR has gone through several generations of development, with each providing more performance and lower power consumption. GDDR6 is the latest generation of graphics memory.

## Ram vs. Cache
Although Cache and RAM both are used to increase the performance of the system there exists a lot of differences in which they operate to increase the efficiency of the system. 

|Ram|Cache|
|---|-----|
|RAM is larger in size compared to cache. Memory ranges from 1MB to 16GB|The cache is smaller in size. Memory ranges from 2KB to a few MB generally.|
|It stores data that is currently processed by the processor.|It holds frequently accessed data.|
OS interacts with secondary memory to get data to be stored in Primary Memory or RAM|OS interacts with primary memory to get data to be stored in Cache.|
It is ensured that data in RAM are loaded before access to the CPU. This eliminates RAM miss never.|CPU searches for data in Cache, if not found cache miss occur.|

## RAM vs. virtual memory
A computer can run short on memory, especially when running multiple programs simultaneously. Operating systems can compensate for physical memory shortfalls by creating virtual memory.

With virtual memory, data is temporarily transferred from RAM to disk storage, and virtual address space is increased using active memory in RAM and inactive memory in an HDD to form contiguous addresses that hold an application and its data. Using virtual memory, a system can load larger programs or multiple programs running at the same time, letting each operate as if it has infinite memory without having to add more RAM.

Virtual memory is able to handle twice as many addresses as RAM. A program's instructions and data are initially stored at virtual addresses, and once the program is executed, those addresses are turned into actual memory addresses.

One downside to virtual memory is that it can slow a computer because data must be mapped between the virtual and physical memory. With physical memory alone, programs work directly from RAM.

## RAM vs. flash memory
Flash memory and RAM are both comprised of solid-state chips. However, they play different roles in computer systems because of differences in the way they're made, their performance specifications and cost. Flash memory is used for storage memory. RAM is used as active memory that performs calculations on the data retrieved from storage.

One significant difference between RAM and flash memory is that data must be erased from NAND flash memory in entire blocks. This makes it slower than RAM, where data can be erased in individual bits.

However, NAND flash memory is less expensive than RAM, and it's also nonvolatile. Unlike RAM, it can hold data even when the power is off. Because of its slower speed, nonvolatility and lower cost, flash is often used for storage memory in SSDs.

## RAM vs. ROM
Read-only memory, or ROM, is computer memory containing data that can only be read, not written to. ROM contains boot-up programming that is used each time a computer is turned on. It generally can't be altered or reprogrammed.

The data in ROM is nonvolatile and isn't lost when the computer power is turned off. As a result, read-only memory is used for permanent data storage. Random Access Memory, on the other hand, can only hold data temporarily. ROM is generally several megabytes of storage, while RAM is several gigabytes.





