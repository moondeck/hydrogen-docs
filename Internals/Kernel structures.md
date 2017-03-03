#Kernel structures

The kernel assumes the first 16 MiB as always taken. Thats where the kernel keeps its structures (Paging, memory allocation, memory detection and other stuff)

Here are some details about the structures:

##CPUID string (at 0x110000)

12 bytes containing a CPUID Leaf 0 string (like GenuineIntel). Null terminated.

##CPUID brand string (at 0x110020)

Up to 48 bytes containing the CPUID brand string. Null terminated.