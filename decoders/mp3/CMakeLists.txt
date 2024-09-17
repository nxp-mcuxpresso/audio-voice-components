if (CONFIG_MCUX_COMPONENT_middleware.audio_voice.components.decoders.mp3)
    mcux_add_include(
        BASE_PATH ${SdkRootDirPath}/middleware/audio_voice/components/decoders/mp3
        INCLUDES .
        CORES cm7f cm33f cm33
        TOOLCHAINS armgcc iar mcux
    )

    mcux_add_source(
        BASE_PATH ${SdkRootDirPath}/middleware/audio_voice/components/decoders/mp3
        SOURCES mp3_cci.h
        CORES cm7f cm33f cm33
        TOOLCHAINS armgcc iar mcux
    )

    mcux_add_library(
        BASE_PATH ${SdkRootDirPath}/middleware/audio_voice/components/decoders/mp3
        LIBS libs/cm7f/armgcc/release/libmp3.a
        CORES cm7f
        TOOLCHAINS armgcc mcux
    )

    mcux_add_library(
        BASE_PATH ${SdkRootDirPath}/middleware/audio_voice/components/decoders/mp3
        LIBS libs/cm33f/armgcc/release/libmp3.a
        CORES cm33f cm33
        TOOLCHAINS armgcc mcux
    )

    mcux_add_library(
        BASE_PATH ${SdkRootDirPath}/middleware/audio_voice/components/decoders/mp3
        LIBS libs/cm7f/iar/release/libmp3.a
        CORES cm7f
        TOOLCHAINS iar
    )

    mcux_add_library(
        BASE_PATH ${SdkRootDirPath}/middleware/audio_voice/components/decoders/mp3
        LIBS libs/cm33f/iar/release/libmp3.a
        CORES cm33f cm33
        TOOLCHAINS iar
    )
endif()