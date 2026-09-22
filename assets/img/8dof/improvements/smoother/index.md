# smoother

the largest reductions in 'legs under one tile'

In general, this patch is expected to introduce **more** 'legs under one tile' - this is coming from moving the search on the tile centers - it is allowed to have one short leg from the actor's position to its tile center, if there is no direct route from actor's position to the next waypoint. Moreover, 8 degrees of freedom allowed for very sharp U-turns, it's clearly visible in the Thieve's Maze. Any reductions in this metric are coming from very bad habit of the old version to hug diagonal walls.

Smoother paths: 589 out of 4663 requests had fewer one-tile legs, showing only 24 exemplary illustrations.


![ar0602_0184](ar0602_0184.webp)

* - *

![ar0602_0198](ar0602_0198.webp)

* - *

![ar0700_0056](ar0700_0056.webp)

* - *

![ar5201_0196](ar5201_0196.webp)

* - *

![ar0146_0026](ar0146_0026.webp)

* - *

![ar0403_0091](ar0403_0091.webp)

* - *

![ar0602_0045](ar0602_0045.webp)

* - *

![ar0602_0051](ar0602_0051.webp)

* - *

![ar0700_0384](ar0700_0384.webp)

* - *

![ar0800_0040](ar0800_0040.webp)

* - *

![ar3400_0211](ar3400_0211.webp)

* - *

![ar5201_0023](ar5201_0023.webp)

* - *

![ar0403_0009](ar0403_0009.webp)

* - *

![ar0403_0346](ar0403_0346.webp)

* - *

![ar0503_0039](ar0503_0039.webp)

* - *

![ar0506_0109](ar0506_0109.webp)

* - *

![ar0510_0010](ar0510_0010.webp)

* - *

![ar0600_0129](ar0600_0129.webp)

* - *

![ar0600_0251](ar0600_0251.webp)

* - *

![ar0602_0124](ar0602_0124.webp)

* - *

![ar0700_0067](ar0700_0067.webp)

* - *

![ar0700_0074](ar0700_0074.webp)

* - *

![ar0700_0083](ar0700_0083.webp)

* - *

![ar0700_0105](ar0700_0105.webp)

* - *
