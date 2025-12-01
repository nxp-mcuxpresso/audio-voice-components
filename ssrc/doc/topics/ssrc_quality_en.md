# SSRC\_Quality\_en

**Definition:**

```
typedef enum
{
    SSRC_QUALITY_HIGH           = 0,
    SSRC_QUALITY_VERY_HIGH      = 1,
    SSRC_QUALITY_DUMMY          = LVM_MAXENUM
} SSRC_Quality_en;

```

**Description:**

Used to select the quality level of the SSRC. For details, see [Performance figures](performance_figures.md). Selecting the highest-quality level, comes with a cost in the SSRC processing requirements. Therefore, it should only be done for critical applications.

**Parent topic:**[Type definitions](#type-definitions)

