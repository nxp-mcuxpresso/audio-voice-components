# SSRC\_GetNrSamples

**Prototype:**

```
SSRC_ReturnStatus_en SSRC_GetNrSamples
   (SSRC_NR_SAMPLES_MODE_en  Mode,
    SSRC_Params_t*           pSSRC_Params );
```

**Description:**

This function retrieves the number of samples or sample pairs for stereo used as an input and as an output of the SSRC module.

|Name|Type|Description|
|:---|:---|:----------|
|Mode|SSRC\_NR\_SAMPLES\_MODE\_en|There are two modes: <br/> - `SSRC_NR_SAMPLES_DEFAULT`: In this mode, the function returns the number of samples for 40 ms blocks<br/> - `SSRC_NR_SAMPLES_MIN`: the function returns the minimal number of samples supported for this conversion ratio. The SSRC\_Init function accepts each integer multiple of this ratio.<br/> Formula: `blocksize (ms) = 1/gcd(Fs_In,Fs_Out)`|
|pSSRC\_Params|SSRC\_Params\_t\*|Pointer to the instance parameters. The application fills in the values of the input sample rate, the output sample rate, and the number of channels. Based on this input, the `SSRC_GetNrSamples` fills in the values for the number of samples for the input and the output audio stream.|

**Returns:**

| <!-- -->    | <!-- -->    |
|-------------|-------------|
|`SSRC_OK`|When the function call succeeds.|
|`SSRC_INVALID_FS`|When the requested input or output sampling rates are invalid.|
|`SSRC_INVALID_NR_CHANNELS`|When the channel format is not equal to `LVM_MONO` or `LVM_STEREO`.|
|`SSRC_NULL_POINTER`|When `pSSRC_Params` is a `NULL` pointer.|
|`SSRC_INVALID_MODE`|When mode is not a valid setting.|

**Note:** The SSRC\_GetNrSamples function returns the values from the following tables. Instead of calling the SSRC\_GetNrSamples function, use the values from these tables directly.

|**Sample rate**|**Nr of samples**|
|:---------------:|:-----------------:|
|8000|320|
|11025|441|
|12000|480|
|16000|640|
|22050|882|
|24000|960|
|32000|1280|
|44100|1764|
|48000|1920|

|**In/Out**|**8000**|**11025**|**12000**|**16000**|**22050**|**24000**|**32000**|**44100**|**48000**|
|:----------:|:--------:|:---------:|:---------:|:---------:|:---------:|:---------:|:---------:|:---------:|-----------|
|**8000**|1<br/>1|320<br/>441|2<br/>3|1<br/>2|160<br/>441|1<br/>3|1<br/>4|80<br/>441|1<br/>6|
|**11025**|441<br/>320|1<br/>1|147<br/>160|441<br/>640|1<br/>2|147<br/>320|441<br/>1280|1<br/>4|147<br/>640|
|**12000**|3<br/>2|160<br/>147|1<br/>1|3<br/>4|80<br/>147|1<br/>2|3<br/>8|40<br/>147|1<br/>4|
|**16000**|2<br/>1|640<br/>441|4<br/>3|1<br/>1|320<br/>441|2<br/>3|1<br/>2|160<br/>441|1<br/>3|
|**22050**|441<br/>160|2<br/>1|147<br/>80|441<br/>320|1<br/>1|147<br/>160|441<br/>640|1<br/>2|147<br/>320|
|**24000**|3<br/>1|320<br/>147|2<br/>1|3<br/>2|160<br/>147|1<br/>1|3<br/>4|80<br/>147|1<br/>2|
|**32000**|4<br/>1|1280<br/>441|8<br/>3|2<br/>1|640<br/>441|4<br/>3|1<br/>1|320<br/>441|2<br/>3|
|**44100**|441<br/>80|4<br/>1|147<br/>40|441<br/>160|2<br/>1|147<br/>80|441<br/>320|1<br/>1|147<br/>160|
|**48000**|6<br/>1|640<br/>147|4<br/>1|3<br/>1|320<br/>147|2<br/>1|3<br/>2|160<br/>147|1<br/>1|

**Parent topic:**[Functions](../topics/functions.md)

