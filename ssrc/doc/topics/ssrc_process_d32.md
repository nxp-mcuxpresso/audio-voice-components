# SSRC\_Process\_D32

**Prototype:**

```
SSRC_ReturnStatus_en SSRC_Process_D32
   (SSRC_Instance_t* pSSRC_Instance,
    LVM_INT32*       pSSRC_AudioIn,
    LVM_INT32*       pSSRC_AudioOut);
```

**Description:**

Process function for the SSRC module. The function takes pointers as input and output audio buffers.

The sample format used for the input and output buffers is 32-bit little-endian. Stereo buffers are interleaved \(L1, R1, L2, R2, and so on\), mono buffers are deinterleaved \(L1, L2, and so on\).

|Name|Type|Description|
|----|----|-----------|
|`pSSRC_Instance`|`SSRC_Instance_t*`|Pointer to the instance of the SSRC.|
|`pSSRC_AudioIn`|`LVM_INT32*`|Pointer to the input samples.|
|`pSSRC_AudioOut`|`LVM_INT32*`|Pointer to the output samples.|

**Returns:**

|`SSRC_OK`|When the function call succeeds.|
|`SSRC_NULL_POINTER`|When one of `pSSRC_Instance`, `pSSRC_AudioIn`, or `pSSRC_AudioOut` is `NULL`.|

**Parent topic:**[Functions](../topics/functions.md)

