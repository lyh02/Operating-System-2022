---
layout: page
title: "homework12"
permalink: /homework/12/
---

<head>
<script type="text/x-mathjax-config">
  MathJax.Hub.Config({
      extensions: ["tex2jax.js"],
      tex2jax: {
          inlineMath: [ ['$','$'], ["\\(","\\)"] ],
          processEscapes: true,
          processRefs: true,
          processEnvironments: true
      },
      TeX: { equationNumbers: { autoNumber: "AMS" } }
  });
</script>
<script type="text/javascript" async
  src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML">
</script>
</head>

# P569: Problems 12.1, 12.2, 12.3, 12.13 (8th Edition)

**12.1** Define:
- B = block size
- R = record size
- P = size of block pointer
- F = blocking factor; expected number of records within a block

Give a formula for F for the three blocking methods depicted in Figure 12.8.

<img src="https://s2.loli.net/2022/12/12/tvh3cW4dgL1kxpq.png" width=600>

**12.2** One scheme to avoid the problem of preallocation versus waste or lack of contiguity is to allocate portions of increasing size as the file grows. For example, begin with a portion size of one block, and double the portion size for each allocation. Consider a file of $n$ records with a blocking factor of $F$, and suppose that a simple one-level index
is used as a file allocation table.
a. Give an upper limit on the number of entries in the file allocation table as a function of $F$ and $n$.
b. What is the maximum amount of the allocated file space that is unused at any time?

**12.3** What file organization would you choose to maximize efficiency in terms of speed of access, use of storage space, and ease of updating (adding/deleting/modifying) when the data are:
- a. updated infrequently and accessed frequently in random order?
- b. updated frequently and accessed in its entirety relatively frequently?
- c. updated frequently and accessed frequently in random order?

**12.13** Consider the organization of a UNIX file as represented by the inode (Figure 12.15). Assume that there are 12 direct block pointers, and a singly, doubly, and triply indirect pointer in each inode. Further, assume that the system block size and the disk sector size are both 8K. If the disk block pointer is 32 bits, with 8 bits to identify the physical disk and 24 bits to identify the physical block, then
- a. What is the maximum file size supported by this system?
- b. What is the maximum file system partition supported by this system?
- c. Assuming no information other than that the file inode is already in main memory, how many disk accesses are required to access the byte in position 13,423,956?

<img src="https://s2.loli.net/2022/12/12/A9eqw8xbhMTlNLX.png" width=600>