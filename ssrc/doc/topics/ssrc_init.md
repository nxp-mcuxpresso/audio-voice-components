# SSRC\_Init

**Prototype:**

```
SSRC_ReturnStatus_en SSRC_Init
   (SSRC_Instance_t* pSSRC_Instance,
    SSRC_Scratch_t*  pSSRC_Scratch,
    SSRC_Params_t*   pSSRC_Params,
    LVM_INT16**      ppInputInScratch,
    LVM_INT16**      ppOutputInScratch);
```

**Description:**

The `SSRC_Init` function initializes an instance of the SSRC module.

|Name|Type|Description|
|----|----|-----------|
|`pSSRC_Instance`|`SSRC_Instance_t*`|Pointer to the instance of the SSRC. This application must allocate the memory before calling the `SSRC_Init` function.|
|`pSSRC_Scratch`|`SSRC_Scratch_t*`|Pointer to the scratch memory. The pointer is saved inside the instance and is used by the `SSRC_Process` function. The application must allocate the scratch memory before calling the `SSRC_Init` function.|
|`pSSRC_Params`|`SSRC_Params_t*`|Pointer to the instance parameters.|
|`ppInputInScratch`|`LVM_INT16**`|The SSRC module can be called with the input samples located in scratch. This pointer points to a location that holds the pointer to the location in the scratch memory that can be used to store the input samples. For example, to save memory.|
|`ppOutputInScratch`|`LVM_INT16**`|The SSRC module can store the output samples in the scratch memory. This pointer points to a location that holds the pointer to the location in the scratch memory that can be used to store the output samples. For example, to save memory.|

**Returns:**

| <!-- -->    | <!-- -->    |
|-------------|-------------|
|`SSRC_OK`|When the function call succeeds.|
|`SSRC_INVALID_FS`|When the requested input or output sampling rates are invalid.|
|`SSRC_INVALID_NR_CHANNELS`|When the channel format is not equal to `LVM_MONO` or `LVM_STEREO`.|
|`SSRC_NULL_POINTER`|When `pSSRC_Params` or `pScratchSize` is a `NULL` pointer.|
|`SSRC_WRONG_NR_SAMPLES`|When the number of samples on the input or on the output are incorrect.|
|`SSRC_ALIGNMENT_ERROR`|When the instance memory or the scratch memory is not 4 bytes aligned.|

**Parent topic:**[Functions](#functions)

