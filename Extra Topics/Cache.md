# Cache 

A **CPU Cache** is a hardware cache used by Central Processitng Unit (**CPU**) **to reduce the average cost (time or energy) to access data** from the **main memory.**

A cache is a **smaller, faster memory, located closer to a processor core**, which **stores copies of the data from frequently used main memory locations**.

Most CPUs have a **hierarchy of multiple cache levels** (**L1**, **L2**, often **L3**, and rarely even **L4**), with **separate** _**instruction-specific**_ and **_data-specific_** caches at level 1.

**L1** caches are usually on the **same die as CPU** 
**L2** caches can often be on a **different die**.

In multi-core CPUs, **each Core has its own L1 cache**, while they share a **L2** cache.

**L1** has **faster access** and **smaller memory** than **L2** cache.

**L1** usually stores **instruction data**, **L2** can store **some shared data**. 


**CPU Threads are often assigned a _Cache Line_ which is part of a cache**.