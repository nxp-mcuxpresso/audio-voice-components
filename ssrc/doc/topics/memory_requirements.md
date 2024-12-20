# Memory requirements

The following are the memory requirements for the SSRC module.

|**Memory item**|**Size in bytes**|
|---------------|-----------------|
|Instance memory \(persistent\)|548|
|Scratch memory \(non-persistent\)|15.536 [1](#fntarg_1)|
|Program memory for Arm9E and XScale|14k|
|Program memory for Arm7|15k|

**Parent topic:**[Resource usage](../topics/resource_usage.md)

[1](#fnsrc_1) Worst case number for I/O buffers of 40 ms. If smaller I/O buffers are used, this number is smaller. The required scratch memory is roughly equal to 2 times the buffer size on the highest sample rate.

