# Function return status

**Definition:**

```
typedef enum
{
    SSRC_OK                     = 0,
    SSRC_INVALID_FS             = 1,
    SSRC_INVALID_NR_CHANNELS    = 2,
    SSRC_NULL_POINTER           = 3,
    SSRC_WRONG_NR_SAMPLES       = 4,
    SSRC_ALLINGMENT_ERROR       = 5,
    SSRC_INVALID_MODE           = 6,
    SSRC_INVALID_VALUE          = 7,
    SSRC_ALLINGMENT_ERROR       = 8,
    LVXXX_RETURNSTATUS_DUMMY = LVM_MAXENUM
} SSRC_ReturnStatus_en;

```

**Description:**

The `SSRC_ReturnStatus_en` enumerated type specifies the different error codes returned by the API functions. For the exact meaning, see the individual function descriptions.

**Parent topic:**[Type definitions](../topics/type_definitions.md)

