# Example application

The source code of the example application can be found in the `.\EX_APP\APP_FileIO\SRC` directory of the release package. The `.\EX_APP\APP_FileIO\MAKE` directory contains a make file that can be used to build the example application. When building the application, an executable is generated in the `.\EX_APP\APP_FileIO\EXE` directory.

The example application takes as command-line input parameters:

1.  The path toward the input PCM file. It assumes raw 16 bit signed little-endian put. Stereo input samples should be interleaved \(L1, L2 R1, R2,…\), mono samples should be deinterleaved \(L1, L2, and so on\).
2.  The path toward the output PCM file.
3.  The input sample rate.
4.  The output sample rate.
5.  The channel format \(mono or stereo\).

