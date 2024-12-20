# SSRC\_GetScratchSize

**Prototype:**

```
SSRC_ReturnStatus_en SSRC_GetScratchSize
   (SSRC_Params_t*    pSSRC_Params,
    LVM_INT32*        pScratchSize );
```

**Description:**

This function retrieves the scratch size for a given conversion ratio and for given buffer sizes at the input and at the output.

|Name|Type|Description|
|:---|:---|:----------|
|`pSSRC_Params`|`SSRC_Params_t*`|Pointer to the instance parameters. All members should have a valid value.|
|`pScratchSize`|`LVM_INT32*`|Pointer to the scratch size. The `SSRC_GetScratchSize` function fills in the correct value \(in bytes\).

|

**Returns:**

| <!-- -->    | <!-- -->    |
|-------------|-------------|
|`SSRC_OK`|When the function call succeeds.|
|`SSRC_INVALID_FS`|When the requested input or output sampling rates are invalid.|
|`SSRC_INVALID_NR_CHANNELS`|When the channel format is not equal to `LVM_MONO` or `LVM_STEREO`.|
|`SSRC_NULL_POINTER`|When `pSSRC_Params` or `pScratchSize` is a `NULL` pointer.|
|`SSRC_WRONG_NR_SAMPLES`|When the number of samples on the input or on the output are incorrect.|

**Parent topic:**[Functions](../topics/functions.md)

