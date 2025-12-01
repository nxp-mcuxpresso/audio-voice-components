# SSRC\_SetGains

**Prototype:**

```
SSRC_ReturnStatus_en SSRC_SetGains
   (SSRC_Instance_t* pSSRC_Instance,
    LVM_Mode_en      bHeadroomGainEnabled,
    LVM_Mode_en      bOutputGainEnabled,
    LVM_INT16       OutputGain);
```

**Description:**

This function sets headroom gain and the post gain of the SSRC. The `SSRC_SetGains` function is an optional function that should be used only in rare cases. Preferably, use the default settings.

|Name|Type|Description|
|----|----|-----------|
|`pSSRC_Instance`|`SSRC_Instance_t*`|Pointer to the instance of the SSRC.|
|`bHeadroomGainEnabled`|`LVM_Mode_en`|Parameter to enable or disable the headroom gain of the SSRC. The default value is `LVM_MODE_ON`. `LVM_MODE_OFF` can be used if it can be guaranteed that the input level is below - 6 in all cases \(the default headroom is -6 dB\).|
|`bOutputGainEnabled`|`LVM_Mode_en`|Parameter to enable or disable the output gain. The default value is `LVM_MODE_ON`.|
|`OutputGain`|`LVM_INT16`|The value of the output gain. The output gain is a linear gain value. 0x7FFF is equal to +6 dB and 0x0000 corresponds to -inf dB. By default, a 3 dB gain is applied \(OutputGain = 23197\), resulting in an overall gain of -3 dB \(-6 dB headroom +3 dB output gain\).<table>  <thead>  <tr>  <th>Unit</th>  <th>Q format</th>  <th>Data Range</th> <th>Default value</th>  </tr>  </thead>  <tbody>  <tr>  <td>Linear gain</td>  <td>Q1.14</td>  <td>\[0;32767\]</td> <td> 23197</td> </tr>  </tbody> </table>|

**Returns:**

| <!-- -->    | <!-- -->    |
|-------------|-------------|
|`SSRC_OK`|When the function call succeeds|
|`SSRC_NULL_POINTER`|When `pSSRC_Instance` is a NULL pointer|
|`SSRC_INVALID_MODE`|Wrong value used for the `bHeadroomGainEnabled` or the `OutputGainEnabled` parameters.|
|`SSRC_INVALID_VALUE`|When `OutputGain` is out of the range \[0;32767\].|

**Parent topic:**[Functions](#functions)

