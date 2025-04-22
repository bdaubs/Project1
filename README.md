# Project1
Project1 for CS351, by Brandon Daubs

TABLE

OPTIMIZATION LEVEL -g
PROGRAM NAME  REAL    USER    SYS    MEMORY (KB)    THROUGHPUT        IMPROVEMENT
hash-00       350.18  343.69  4.51   2900           8.28 KB/S         N/A
hash-01       17.86   16.42   1.31   2884           161.48 KB/S       19.61
hash-02       15.66   14.25   1.3    3468           221.46 KB/S       22.36 
hash-03       16.48   15.13   1.22   2900           175.98 KB/S       21.25
hash-04       14.35   13.65   0.54   5011208        349,213.10 KB/S   24.40 

OPTIMIZATION LEVEL -02
PROGRAM NAME  REAL    USER    SYS    MEMORY (KB)    THROUGHPUT        IMPROVEMENT
hash-00       344.83  333.06  7.54   2892           8.39 KB/S         N/A
hash-01       8.29    6.89    1.33   3468           418.34 KB/S       41.6
hash-02       8.18    6.88    1.22   3456           422.49 KB/S       42.16
hash-03       8.13    6.85    1.2    3456           425.09 KB/S       42.41 
hash-04       7.25    6.62    0.55   5012368        691,361.10 KB/S   47.56 

1) What operation do you think accounts for most of hash-00's runtime?
   Each of numHashes number of hashes is hashed one byte at a time.
2) hash-01 and hash-02 both dynamically allocate memory for each hash computation.  Is there much difference time-wise between their two allocation methods?
   There is not a ton of difference but hash-02 seems to take a small amount less time than hash-01.
3) hash-03 avoids the allocation by using a fixed-size array.  Is there an appreciable speed difference?
    There does not appear to be a large time difference when using a fixed-size array.
4) Why is hash-04's memory usage so much larger than any of the other versions?  Hint: recall when we discussed how the operating system reads a file and makes it available to an application.  Specifically, the O/S will transfer data from disk to its own memory, and then copy from there into buffers provided by the application.  In the memory map case, the O/S is merely sharing the copy of the file's data that is in its (the O/S's) memory, and not making an additional copy from its memory into memory only in the application
   It looks like hash-04 is hashing every byte of each hash all at once as opposed to doing it a piece at a time.
5) What other compiler options did you try, and did they help at all?
   I also tried compiler optimization -03, and it did reduce the runtime of the hash-00 program a bit further, but it didn't seem to have much of an appreciable effect on the other programs.
