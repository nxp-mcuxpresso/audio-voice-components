# LVM\_Format\_en

**Definition:**

```
typedef enum
{
    LVM_STEREO          = 0,
    LVM_MONOINSTEREO    = 1,
    LVM_MONO            = 2
} LVM_Format_en;
```

**Description:**

The `LVM_Format_en` enumerated type is used to set the value of the SSRC data format.

The SSRC supports input data in two formats Mono and Stereo. For an input buffer of `NumSamples = N` \(meaning `N` sample pairs for Stereo and MonoInStereo or N samples for Mono\), the format of data in the buffer is as listed in [Table 1](#table_rrd_r1h_rxb):

|**Sample Number**|**Stereo**|**MonoInStereo**|**Mono**|
|:---------------:|:--------:|:--------------:|:------:|
|0|Left\(0\)|Mono\(0\)|Mono\(0\)|
|1|Right\(0\)|Mono\(0\)|Mono\(1\)|
|2|Left\(1\)|Mono\(1\)|Mono\(2\)|
|3|Right\(1\)|Mono\(1\)|Mono\(3\)|
|4|Left\(2\)|Mono\(2\)|Mono\(4\)|
|“|“|“|“|
|“|“|“|“|
|N-2|Left\(N/2-1\)|Mono\(N/2-1\)|Mono\(N-2\)|
|N-1|Right\(N/2-1\)|Mono\(N/2-1\)|Mono\(N-1\)|
|N|Left\(N/2\)|Mono\(N/2\)|Not Used|
|N+1|Right\(N/2\)|Mono\(N/2\)|Not Used|
|N+2|Left\(N/2+1\)|Mono\(N/2+1\)|Not Used|
|N+3|Right\(N/2+1\)|Mono\(N/2+1\)|Not Used|
|“|“|“|Not Used|
|“|“|“|Not Used|
|2\*N-2|Left\(N-1\)|Mono\(N-1\)|Not Used|

**Parent topic:**[Type definitions](../topics/type_definitions.md)

