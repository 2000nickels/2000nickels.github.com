---
layout: post
title: "A Cray for $35"
date: 2012-10-05 06:27
comments: true
categories: 
---

Since the new Raspbian distribution has hardware accelerated floating
point operations, I wanted to test how fast the Raspberry Pi can run.
But what to use for a benchmark?  Well,
[LINPACK](http://en.wikipedia.org/wiki/LINPACK_benchmarks) is the
historical choice for evaluating floating point performance.  Sure,
the Pi doesn't come with a FORTRAN compiler, but there is a C version
of the benchmark that I got to compile with a [few minor
changes](https://github.com/2000nickels/linpackc).


## After the update to Raspbian 2012-09-18, but no overclocking ##

    pi@raspberrypi ~/linpackc $ ./linpackc 
    
    Rolled Double Precision Linpack
    
         norm. resid      resid           machep         x[0]-1        x[n-1]-1
           1.7        7.41628980e-14  2.22044605e-16 -1.49880108e-14 -1.89848137e-14
        times are reported for matrices of order   100
          dgefa      dgesl      total       kflops     unit      ratio
     times for array with leading dimension of  201
           0.02       0.00       0.02      34333       0.06       0.36
           0.01       0.00       0.01      68667       0.03       0.18
           0.01       0.00       0.01      68667       0.03       0.18
           0.02       0.00       0.02      40655       0.05       0.30
     times for array with leading dimension of 200
           0.02       0.00       0.02      34333       0.06       0.36
           0.02       0.00       0.02      34333       0.06       0.36
           0.01       0.00       0.01      68667       0.03       0.18
           0.02       0.00       0.02      42256       0.05       0.29
    Rolled Double  Precision 40655 Kflops ; 1000 Reps 
       

## After enabling Turbo mode ##

To enable the Turbo mode, use the following command:

    sudo raspi-config

Under the overclocking???? section, choose the "Turbo" option:

      Turbo  1000MHz ARM, 500MHz core, 500MHz SDRAM, 6 overvolt

Then select "Finsh", and then say "Yes" when it raspi-config asks to reboot.



    pi@raspberrypi ~/linpackc $ ./linpackc 

    Rolled Double Precision Linpack

	 norm. resid      resid           machep         x[0]-1        x[n-1]-1
	   1.7        7.41628980e-14  2.22044605e-16 -1.49880108e-14 -1.89848137e-14
	times are reported for matrices of order   100
	  dgefa      dgesl      total       kflops     unit      ratio
     times for array with leading dimension of  201
	   0.01       0.00       0.01      68667       0.03       0.18
	   0.01       0.00       0.01      68667       0.03       0.18
	   0.01       0.00       0.01      68667       0.03       0.18
	   0.01       0.00       0.01      62709       0.03       0.20
     times for array with leading dimension of 200
	   0.01       0.00       0.01      68667       0.03       0.18
	   0.01       0.00       0.01      68667       0.03       0.18
	   0.01       0.00       0.01      68667       0.03       0.18
	   0.01       0.00       0.01      65149       0.03       0.19
    Rolled Double  Precision 62709 Kflops ; 1000 Reps 

And checking the CPU temperature:

    pi@raspberrypi ~/linpackc $ cat /sys/class/thermal/thermal_zone0/temp 
    46540

So, that's 46.540 degrees C.  See http://www.raspberrypi.org/phpBB3/viewtopic.php?f=29&t=6201&start=325#p173006


Here are the comparison numbers from the [Linpack Benchmark Report](http://www.netlib.org/utk/people/JackDongarra/faq-linpack.html#_Toc27885750):

Year | Computer |MFLOPS
----:|:---------|------:
1988 | CRAY Y-MP | 74
**2012** | **Raspberry Pi (Turbo mode)** | **63**
1987 | ETA 10-E | 52
1986 | NEC SX-2 | 46
1985 | NEC SX-2 | 46
**2012** | **Raspberry Pi (Stock)** | **41**
1984 | CRAY X-MP | 21
1983 | CRAY 1 | 12
1979 | CRAY 1 | 3.4


So, the Raspberry Pi that you bought for $35 is the number-crunching
equivalent of a Cray X-MP.  Taken that is from 1984, but remember that 
today's $35 dollars is only $15 in 1984.


