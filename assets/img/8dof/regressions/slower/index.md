# slower

the search cost more time

Keep in mind it's only a hint, as I took only one sample per request, on one machine.

This patch is **expected to be slower**, as it is doing in general more work than before (2x more frontier tiles per iteration, actually respecting non-bumpable actors on walkability lines, more robust open-set's priority queue, post-process path straightening pass). However, there are some parts of the system more optimized now - per-node heuristic is cheaper, traversability cache is simplified, search is now done in searchmap space). In some scenarios it yields faster calculations, but in the big maps and long paths it will just be slower.

Slower paths: 1332 out of 5200 requests searched slower, showing only 24 exemplary illustrations.

![ar0403_0288](ar0403_0288.webp)

*AR0403 ar0403_0288 - 4 -> 2978 us  (x717.7)*

![ar0403_0111](ar0403_0111.webp)

*AR0403 ar0403_0111 - 1 -> 558 us  (x541.6)*

![ar0503_0207](ar0503_0207.webp)

*AR0503 ar0503_0207 - 0 -> 69 us  (x462.4)*

![ar5201_0376](ar5201_0376.webp)

*AR5201 ar5201_0376 - 0 -> 59 us  (x370.1)*

![ar0503_0335](ar0503_0335.webp)

*AR0503 ar0503_0335 - 11 -> 1785 us  (x164.7)*

![ar1000_0279](ar1000_0279.webp)

*AR1000 ar1000_0279 - 5 -> 247 us  (x48.3)*

![ar0403_0279](ar0403_0279.webp)

*AR0403 ar0403_0279 - 4 -> 56 us  (x15.0)*

![ar0503_0123](ar0503_0123.webp)

*AR0503 ar0503_0123 - 8 -> 79 us  (x10.4)*

![ar0146_0056](ar0146_0056.webp)

*AR0146 ar0146_0056 - 379 -> 3416 us  (x9.0)*

![ar0146_0304](ar0146_0304.webp)

*AR0146 ar0146_0304 - 249 -> 2149 us  (x8.6)*

![ar0146_0001](ar0146_0001.webp)

*AR0146 ar0146_0001 - 305 -> 2526 us  (x8.3)*

![ar0800_0042](ar0800_0042.webp)

*AR0800 ar0800_0042 - 78 -> 522 us  (x6.7)*

![ar0700_0131](ar0700_0131.webp)

*AR0700 ar0700_0131 - 1005 -> 6101 us  (x6.1)*

![ar0602_0397](ar0602_0397.webp)

*AR0602 ar0602_0397 - 905 -> 5319 us  (x5.9)*

![ar0510_0051](ar0510_0051.webp)

*AR0510 ar0510_0051 - 19 -> 107 us  (x5.8)*

![ar0146_0296](ar0146_0296.webp)

*AR0146 ar0146_0296 - 369 -> 2113 us  (x5.7)*

![ar0146_0315](ar0146_0315.webp)

*AR0146 ar0146_0315 - 128 -> 663 us  (x5.2)*

![ar0146_0036](ar0146_0036.webp)

*AR0146 ar0146_0036 - 489 -> 2425 us  (x5.0)*

![ar0400_0399](ar0400_0399.webp)

*AR0400 ar0400_0399 - 549 -> 2641 us  (x4.8)*

![ar5201_0266](ar5201_0266.webp)

*AR5201 ar5201_0266 - 23 -> 100 us  (x4.4)*

![ar0602_0057](ar0602_0057.webp)

*AR0602 ar0602_0057 - 982 -> 3966 us  (x4.0)*

![ar0403_0398](ar0403_0398.webp)

*AR0403 ar0403_0398 - 13 -> 53 us  (x4.0)*

![ar1000_0101](ar1000_0101.webp)

*AR1000 ar1000_0101 - 65 -> 240 us  (x3.7)*

![ar0700_0360](ar0700_0360.webp)

*AR0700 ar0700_0360 - 2984 -> 10667 us  (x3.6)*
