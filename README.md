# MCUXpresso SDK : audio-voice-components

## Overview
This repository is for MCUXpresso SDK audio-voice-components middleware delivery and it contains the components officially provided in NXP MCUXpresso SDK. This repository is part of the MCUXpresso SDK overall delivery which is composed of several sub-repositories/projects. Navigate to the top/parent repository (mcuxsdk-manifests) for the complete delivery of MCUXpresso SDK.

## Documentation
Overall details can be reviewed here: [MCUXpresso SDK Online Documentation](https://mcuxpresso.nxp.com/mcuxsdk/latest/html/introduction/README.html)

Visit [Audio Voice Components - Documentation](https://mcuxpresso.nxp.com/mcuxsdk/latest/html/middleware/audio_voice/components/index.html) to review details on the contents in this sub-repo.

## Setup
Instructions on how to install the MCUXpresso SDK provided from GitHub via west manifest [Getting Started with SDK - Detailed Installation Instructions](https://mcuxpresso.nxp.com/mcuxsdk/latest/html/gsd/installation.html#installation)

## Contribution
Contributions are not currently accepted. Guidelines to contribute will be posted in the future.

---------------------------------

## Overview

This repository allows users to add additional functionality to the [Maestro Audio framework](https://github.com/nxp-mcuxpresso/maestro). This structure is designed for integration with Maestro and is not intended for standalone use. For information on the use of individual components, please refer to the Maestro [programmer's guide](https://github.com/nxp-mcuxpresso/maestro/blob/main/doxygen/ProgrammersGuide.md).

This repository acts as Zephyr module, to be able to use these libraries in Zephyr build system.

## Content
* [asrc](#asynchronous-sample-rate-converter) - Libraries and public files of Asynchronous Sample Rate Converter, version 1.0.0
* [ssrc](#synchronous-sample-rate-converter) - Libraries and public files of Synchronous Sample Rate Converter, version 1.0.0
* [opus](#opus) - Source files of Opus decoder and encoder, version 1.3.1
* [opusfile](#opus-file) - Source files for Opus streams in the Ogg container, version 0.12
* [ogg](#ogg-container) - Source files of Ogg container, version 1.3.5
* [decoders](#decoders) - Libraries and public files of following audio decoders:
    * [aac](#aac) -  AAC decoder, version 1.0.0
    * [flac](#flac) - FLAC decoder, version 1.0.0
    * [mp3](#mp3) - MP3 decoder, version 1.0.0
    * [wav](#wav) - WAV decoder, version 1.0.0
* zephyr/ - Files allowing usage of the libraries in Zephyr build

Following table contains information about libraries and source files availability:

<table class="tg"><thead>
  <tr>
    <th class="tg-1lax" rowspan="2"></th>
    <th class="tg-1lax" colspan="2">Processor</th>
    <th class="tg-1lax" colspan="2">Toolchain</th>
    <th class="tg-1lax" rowspan="2">Source files</th>
  </tr>
  <tr>
    <th class="tg-1lax">Cortex-M7(F)</th>
    <th class="tg-1lax">Cortex-M33(F)</th>
    <th class="tg-1lax">ARM GCC</th>
    <th class="tg-1lax">IAR</th>
  </tr></thead>
<tbody>
  <tr>
    <td class="tg-1lax">ASRC</td>
    <td class="tg-0lax">Yes</td>
    <td class="tg-0lax">X<br></td>
    <td class="tg-0lax">Yes</td>
    <td class="tg-0lax">X</td>
    <td class="tg-0lax">X</td>
  </tr>
  <tr>
    <td class="tg-1lax">SSRC</td>
    <td class="tg-0lax">Yes</td>
    <td class="tg-0lax">Yes</td>
    <td class="tg-0lax">Yes</td>
    <td class="tg-0lax">Yes</td>
    <td class="tg-0lax">X</td>
  </tr>
    <tr>
    <td class="tg-1lax">Opus</td>
    <td class="tg-0lax">X</td>
    <td class="tg-0lax">X</td>
    <td class="tg-0lax">X</td>
    <td class="tg-0lax">X</td>
    <td class="tg-0lax">Yes</td>
  </tr>
    <tr>
    <td class="tg-1lax">Opus File</td>
    <td class="tg-0lax">X</td>
    <td class="tg-0lax">X</td>
    <td class="tg-0lax">X</td>
    <td class="tg-0lax">X</td>
    <td class="tg-0lax">Yes</td>
  </tr>
    </tr>
    <tr>
    <td class="tg-1lax">Ogg Container</td>
    <td class="tg-0lax">X</td>
    <td class="tg-0lax">X</td>
    <td class="tg-0lax">X</td>
    <td class="tg-0lax">X</td>
    <td class="tg-0lax">Yes</td>
  </tr>
    <tr>
    <td class="tg-1lax">AAC</td>
    <td class="tg-0lax">Yes</td>
    <td class="tg-0lax">Yes</td>
    <td class="tg-0lax">Yes</td>
    <td class="tg-0lax">X</td>
    <td class="tg-0lax">X</td>
  </tr>
    <tr>
    <td class="tg-1lax">FLAC</td>
    <td class="tg-0lax">Yes</td>
    <td class="tg-0lax">Yes</td>
    <td class="tg-0lax">Yes</td>
    <td class="tg-0lax">Yes</td>
    <td class="tg-0lax">X</td>
  </tr>
    </tr>
    <tr>
    <td class="tg-1lax">MP3</td>
    <td class="tg-0lax">Yes</td>
    <td class="tg-0lax">Yes</td>
    <td class="tg-0lax">Yes</td>
    <td class="tg-0lax">Yes</td>
    <td class="tg-0lax">X</td>
  </tr>
    </tr>
    <tr>
    <td class="tg-1lax">WAV</td>
    <td class="tg-0lax">Yes</td>
    <td class="tg-0lax">Yes</td>
    <td class="tg-0lax">Yes</td>
    <td class="tg-0lax">Yes</td>
    <td class="tg-0lax">X</td>
  </tr>
</tbody>
</table>

## Asynchronous Sample Rate Converter
The Asynchronous Sample Rate Converter (ASRC) software module compensates the drift
between two mono audio signals. This is not a frequency converter and so the nominal signal
frequency is the same before and after the ASRC.
More details about ASRC are available in the User Guide, which is located in `asrc\doc\`.

## Synchronous Sample Rate Converter
The Synchronous Sample Rate Converter (SSRC) software module converts an audio signal
(mono or stereo) with a certain sampling frequency to an audio signal with another sampling
frequency.
More details about SSRC are available in the [User Guide](ssrc/doc/ugindex.md).

## Opus
For Opus decoder and encoder documentation please see following link: [opus](https://opus-codec.org/docs/opus_api-1.3.1/).

## Opus File
The Opus File provides a API for decoding and basic manipulation of Opus streams in Ogg container and depends on [Opus](#opus) and [Ogg](#ogg-container) libraries.
For Opus File documentation please see following link: [opusfile](https://opus-codec.org/docs/opusfile_api-0.12/index.html).

## Ogg Container
For Ogg container documentation please see following link: [ogg](https://xiph.org/ogg/doc/).



## Decoders
Each decoder contains libraries for supported processor and toolchain (see table above), corresponding Public API file and documentation folder.
### AAC
For decoder features please see [aacdec](decoders/aac/doc/aacdec.md), for API Usage please see [aacd_ug](decoders/aac/doc/aacd_ug.md).

### FLAC
For decoder features please see [flacdec](decoders/flac/doc/flacdec.md), for API Usage please see [flacd_ug](decoders/flac/doc/flacd_ug.md).
### MP3
For decoder features please see [mp3dec](decoders/mp3/doc/mp3dec.md), for API Usage please see [mp3d_ug](decoders/mp3/doc/mp3d_ug.md).
### WAV
For decoder features please see [wavdec](decoders/wav/doc/wavdec.md), for API Usage please see [wavd_ug](decoders/wav/doc/wavd_ug.md).

## Zephyr build

To add library into the Zephyr build, add `CONFIG_NXP_AUDIO_VOICE_COMPONENTS_*` for specific libraries into your prj.conf.
For all configuration options, see [zephyr/Kconfig](zephyr/Kconfig).

List of supported libraries in Zephyr:
- Decoders:
  - AAC
  - FLAC
  - MP3
  - FLAC
  - OPUS
- Encoders
  - OPUS
