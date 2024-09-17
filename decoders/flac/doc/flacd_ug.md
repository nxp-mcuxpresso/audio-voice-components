API Usage of FLAC Decoder
================
@ingroup flacdec

# Overview

* This section describes the integration steps to call FLAC decoder APIs by the application code. During each step the used data structures and functions are explained. All cci public APIs are defined in flac_cci.h header file. This file is located at `\decoders\flac\include`.

# Configuration
## Build Options
* SUPPORT_16_BITS_ONLY :- This macro is used to enable 16bits per sample flac decoder.
* _ASM_ :- This macro is used to enable ARM assembly macros for 24bits per sample flac decoder. 

# Buffer Allocation
* The FLAC decoder does not perform dynamic memory allocation. The application calls the function FLACDecoderGetMemorySize() to get the decoder memory requirements. This function must be called before all other decoder functions are invoked.
* The application first gets the required memory size for the decoder and then allocates memory for the decoder structures. Structures contain Main Decoder parameters and decoder information parameters.
* This function populates the required memory for the decoder and returns the required memory size in bytes.

# Initialization
* FLACDecoderInit() function must be called before decode API. This API allocates the memory to decoder main structure and also initializes the decoder main structure parameters. 
* It also registers the call back functions to the decoder, which will be used by decoder to read or to seek the input stream. 

# Decoding
* FLACDecoderDecode() function is main decoding API of the decoder. This API decodes the encoded input stream and fills the PCM output samples into decoder output PCM buffer. 
* This API gives the information about the number of samples produced by the decoder and also provides the pointer to the decoder output PCM samples buffer.  

# Seeking
* FLACDecoderSeek() function calculates the actual frame boundary align offset from the unalign seek offset and returns the actual seek offset. It also resets the decoder internal states and variables.

# Callback Usage
All the callback functions will be assigned to the respective pointers before the codec initialization is called. Callback APIs are described below.

## Read Callback API
FLAC Decoder read call back API reads the bytes from the input stream and fills them into decoder internal bit stream buffer. It returns the number of bytes read from the input stream.

## Seek Callback API
This call back API is for the seek operation.

## Get File Position Callback API
This call back API gives the current file position.



