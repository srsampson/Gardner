#### Gardner - A Gardner Timing Error Detector (TED) Algorithm

I created this based on GNU Radio code, and some deque code by Yash Tulsiani.   

In main() setup with:   
```
    create_timing_error_detector();
```
When you're done, use:   
```
    destroy_timing_error_detector();
```
Then in your demodulation code:   
```
    /*
     * Decimate before TED calculation to get to two samples per symbol
     * For example decimate by 4 after converting to baseband and filtering
     * and say 8 samples per symbol
     */
    for (int i = 0; i < 8; i += 4)
    {
        ted_input(&recvBlock[i]);
    }

    complex float decision = getMiddleSample(); // use middle TED sample
 ```
 #### Deque Algorithm
 A linear collection of complex signal samples that supports element insertion and removal at both ends. The name deque is short for "double ended queue" and is usually pronounced "deck".
 
