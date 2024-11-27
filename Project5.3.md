CHIP Computer {

    IN reset;
    PARTS:
    ROM32K(address=pc-output, out=program-memory-output);
    CPU(inM=data-memory-output, instruction=program-memory-output, reset=reset, outM=data-memory-input, writeM=write-data-memory, addressM=data-memory-address, pc=pc-output);
    Memory(in=data-memory-input, load=write-data-memory, address=data-memory-address, out=data-memory-output);
    
}

![image](https://github.com/user-attachments/assets/6618ad27-1ac2-4ca7-a8d4-3e39a31b378b)
