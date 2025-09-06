
## Load-Store architecture

the ALU that is the arithmetic and logical unit where the arithmetic and logical operations will be performed.

another one is the memory block from which the data will be retrieved and then it will be stored.

problem?

in modern day processors if you want to load some data from the memory block of the processor it cannot be directly loaded from memory to the ALU unit this is because if in case there is `any misbehavior in the ALU process` or `if there is any power failure` or if there is any flaws in program there is high possibility of memory being corrected directly this is because the memory is directly read from the memory block and it is processed in the Ala unit.

Solution:

modern day processors most widely use registers in between the memory and the AL do process that is the data from the memory which needs to be processed will be stored in a registers temporarily and then from that registers the ALU operations will be performed so this registers are much faster than memory in

so using a load instruction we will be loading the data that is required from

## Storing data
the storing process of processed data to the memory
so the storing operation also cannot happen without registers in this modern