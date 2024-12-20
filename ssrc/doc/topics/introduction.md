# Introduction

The Synchronous Sample Rate Converter \(SSRC\) software module converts a mono or stereo audio signal with a certain sampling frequency to an audio signal with a different sampling frequency. The sample rate converter works synchronously, meaning that input and output sampling rates are exactly known for a mutual clock reference.

To accomplish a professional sampling conversion quality and minimal system footprint, the SRC SW module contains highly optimized components.

The SSRC module supports the following features.

-   Multiple instances of the sample rate converter can run at the same time.
-   Supported sampling frequencies: 32 kHz, 44.1 kHz, and 48 kHz plus the halves and the quarters of these three sample rates. The input and output sample rates are freely selectable out of the supported sampling rates
-   Selectable Mono/Stereo Input/Output.
-   Selectable quality level: high quality/ very high quality.


```{include} ../topics/abbreviations_and_references.md
:heading-offset: 1
```

```{include} ../topics/performance_figures.md
:heading-offset: 1
```

```{include} ../topics/resource_usage.md
:heading-offset: 1
```

