# Lab 1 Report

## DEVICE QUERY
```
~/.../lab/device_query $ ./device_query 
Finding OpenCL Platforms...
Found 1 platforms!
Platform 0
- Name: ARM Platform
- Version: OpenCL 3.0 v1.r47p0-01eac0.cd24a10f5ddffa4cfe272051060e786b
- Vendor: ARM
- Num Devices: 1
        Device: 0
        - Name: Mali-G710 r0p0
        - Type: GPU
        - Compute units: 7
        - Global memory size: 3007101952 bytes (2867 MB)
        - Max constant buffer size: 3007101952 bytes (2867 MB)
        - Max local memory size per Compute Unit: 32768 bytes (32 KB)
        - Max Work Item Dimensions: 3
        - Max Work Item size: 1024 x 1024 x 1024 
        - Max group size: 1024
```

## Raytracer Sequential
```
~/.../lab/raytracer_sequential $ make run
./raytracer_sequential
Starting Sequential Ray Tracing...
========================================================
Single-Threaded Implementation on CPU
Total execution time (host + kernel): 809.902 ms
========================================================
```

## Raytracer Parallel
```
~/.../lab/raytracer_parallel $ make gpu
./raytracer_parallel gpu

========================================================
Device: Mali-G710 r0p0
Total execution time (host + kernel): 313.442 ms
Image titled output_gpu.png has been created/modified and can now be viewed!
========================================================
```

### Thoughts on OpenCL
What this lab was able to show me was that OpenCL allows the user to take advantage of dedicated hardware suited for parallel processing. This speeds up parallelizable equations that would normally take a sequential process longer to produce an output. The time difference in both Raytracer_Sequential and Raytracer_Parallel shows the level of efficiency between the two process methods.

## Homework 1
My work can be attributed to the help from the following Youtube videos, the rest of the series were also super helpful in understanding the concepts applied:
https://youtu.be/RKyhHonQMbw?list=PLhqBhHU0mKh9zeei8cdnEe4I5e6ZMNlqy
https://youtu.be/ROTE_yjRi9s?list=PLiwt1iVUib9s6vyEqdpcgAq7NBRlp9mAY

Here are the following outputs of including the "time" command when running "make run" with floats, integers, and doubles, in that order.

### Floats
```
~/.../homework/vector_add $ time make run
./solution Dataset/0/input0.raw Dataset/0/input1.raw Dataset/0/output.raw output.raw
!!SOLUTION IS CORRECT!!
./solution Dataset/1/input0.raw Dataset/1/input1.raw Dataset/1/output.raw output.raw
!!SOLUTION IS CORRECT!!
./solution Dataset/2/input0.raw Dataset/2/input1.raw Dataset/2/output.raw output.raw
!!SOLUTION IS CORRECT!!
./solution Dataset/3/input0.raw Dataset/3/input1.raw Dataset/3/output.raw output.raw
!!SOLUTION IS CORRECT!!
./solution Dataset/4/input0.raw Dataset/4/input1.raw Dataset/4/output.raw output.raw
!!SOLUTION IS CORRECT!!
./solution Dataset/5/input0.raw Dataset/5/input1.raw Dataset/5/output.raw output.raw
!!SOLUTION IS CORRECT!!
./solution Dataset/6/input0.raw Dataset/6/input1.raw Dataset/6/output.raw output.raw
!!SOLUTION IS CORRECT!!
./solution Dataset/7/input0.raw Dataset/7/input1.raw Dataset/7/output.raw output.raw
!!SOLUTION IS CORRECT!!
./solution Dataset/8/input0.raw Dataset/8/input1.raw Dataset/8/output.raw output.raw
!!SOLUTION IS CORRECT!!
./solution Dataset/9/input0.raw Dataset/9/input1.raw Dataset/9/output.raw output.raw
!!SOLUTION IS CORRECT!!

real    0m6.981s
user    0m5.876s
sys     0m0.988s
```

### Integers
```
~/.../homework/vector_add $ time make run
./solution Dataset/0/input0.raw Dataset/0/input1.raw Dataset/0/output.raw output.raw
!!SOLUTION IS CORRECT!!
./solution Dataset/1/input0.raw Dataset/1/input1.raw Dataset/1/output.raw output.raw
!!SOLUTION IS CORRECT!!
./solution Dataset/2/input0.raw Dataset/2/input1.raw Dataset/2/output.raw output.raw
!!SOLUTION IS CORRECT!!
./solution Dataset/3/input0.raw Dataset/3/input1.raw Dataset/3/output.raw output.raw
!!SOLUTION IS CORRECT!!
./solution Dataset/4/input0.raw Dataset/4/input1.raw Dataset/4/output.raw output.raw
!!SOLUTION IS CORRECT!!
./solution Dataset/5/input0.raw Dataset/5/input1.raw Dataset/5/output.raw output.raw
!!SOLUTION IS CORRECT!!
./solution Dataset/6/input0.raw Dataset/6/input1.raw Dataset/6/output.raw output.raw
!!SOLUTION IS CORRECT!!
./solution Dataset/7/input0.raw Dataset/7/input1.raw Dataset/7/output.raw output.raw
!!SOLUTION IS CORRECT!!
./solution Dataset/8/input0.raw Dataset/8/input1.raw Dataset/8/output.raw output.raw
!!SOLUTION IS CORRECT!!
./solution Dataset/9/input0.raw Dataset/9/input1.raw Dataset/9/output.raw output.raw
!!SOLUTION IS CORRECT!!

real    0m6.909s
user    0m5.958s
sys     0m0.843s
```

### Double
```
~/.../homework/vector_add $ time make run
./solution Dataset/0/input0.raw Dataset/0/input1.raw Dataset/0/output.raw output.raw
!!SOLUTION IS CORRECT!!
./solution Dataset/1/input0.raw Dataset/1/input1.raw Dataset/1/output.raw output.raw
!!SOLUTION IS CORRECT!!
./solution Dataset/2/input0.raw Dataset/2/input1.raw Dataset/2/output.raw output.raw
!!SOLUTION IS CORRECT!!
./solution Dataset/3/input0.raw Dataset/3/input1.raw Dataset/3/output.raw output.raw
!!SOLUTION IS CORRECT!!
./solution Dataset/4/input0.raw Dataset/4/input1.raw Dataset/4/output.raw output.raw
!!SOLUTION IS CORRECT!!
./solution Dataset/5/input0.raw Dataset/5/input1.raw Dataset/5/output.raw output.raw
!!SOLUTION IS CORRECT!!
./solution Dataset/6/input0.raw Dataset/6/input1.raw Dataset/6/output.raw output.raw
!!SOLUTION IS CORRECT!!
./solution Dataset/7/input0.raw Dataset/7/input1.raw Dataset/7/output.raw output.raw
!!SOLUTION IS CORRECT!!
./solution Dataset/8/input0.raw Dataset/8/input1.raw Dataset/8/output.raw output.raw
!!SOLUTION IS CORRECT!!
./solution Dataset/9/input0.raw Dataset/9/input1.raw Dataset/9/output.raw output.raw
!!SOLUTION IS CORRECT!!

real    0m6.998s
user    0m5.865s
sys     0m0.934s
```

### Conclusion
I expected double to take slightly longer in processing due to its increased size, but I see no significant change in performance between integer, float, and double processing.
