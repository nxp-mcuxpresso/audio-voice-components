if (CONFIG_MCUX_COMPONENT_middleware.audio_voice.components.decoders.wav)
    mcux_add_include(
        BASE_PATH ${SdkRootDirPath}/middleware/audio_voice/components/decoders/wav
        INCLUDES .
        CORES cm7f cm33f cm33
        TOOLCHAINS armgcc iar mcux
    )

    mcux_add_source(
        BASE_PATH ${SdkRootDirPath}/middleware/audio_voice/components/decoders/wav
        SOURCES wav_cci.h
        CORES cm7f cm33f cm33
        TOOLCHAINS armgcc iar mcux
    )

    mcux_add_library(
        BASE_PATH ${SdkRootDirPath}/middleware/audio_voice/components/decoders/wav
        LIBS libs/cm7f/armgcc/release/libwav.a
        CORES cm7f
        TOOLCHAINS armgcc mcux
    )

    mcux_add_library(
        BASE_PATH ${SdkRootDirPath}/middleware/audio_voice/components/decoders/wav
        LIBS libs/cm33f/armgcc/release/libwav.a
        CORES cm33f cm33
        TOOLCHAINS armgcc mcux
    )

    mcux_add_library(
        BASE_PATH ${SdkRootDirPath}/middleware/audio_voice/components/decoders/wav
        LIBS libs/cm7f/iar/release/libwav.a
        CORES cm7f
        TOOLCHAINS iar
    )

    mcux_add_library(
        BASE_PATH ${SdkRootDirPath}/middleware/audio_voice/components/decoders/wav
        LIBS libs/cm33f/iar/release/libwav.a
        CORES cm33f cm33
        TOOLCHAINS iar
    )
endif()