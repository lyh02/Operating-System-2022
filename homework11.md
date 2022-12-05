---
layout: page
title: "homework11"
permalink: /homework/11/
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

# P520: Problems 11.1, 11.2, 11.3 (8th Edition)

**11.1** Consider a program that accesses a single I/O device and compare unbuffered I/O to the use of a buffer. Show that the use of the buffer can reduce the running time by at most a factor of two.

**11.2** Generalize the result of Problem 11.1 to the case in which a program refers to n devices.

**11.3** Answer the questions below.
- a. Perform the same type of analysis as that of Table 11.2 for the following sequence of disk track requests: 27, 129, 110, 186, 147, 41, 10, 64, 120. Assume that the disk head is initially positioned over track 100 and is moving in the direction of decreasing track number.
- b. Do the same analysis, but now assume that the disk head is moving in the direction of increasing track number.
