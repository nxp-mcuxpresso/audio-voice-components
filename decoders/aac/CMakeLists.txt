if (CONFIG_MCUX_COMPONENT_middleware.audio_voice.components.decoders.aac)
    mcux_add_include(
        BASE_PATH ${SdkRootDirPath}/middleware/audio_voice/components/decoders/aac
        INCLUDES .
        CORES cm7f cm33f cm33
        TOOLCHAINS armgcc mcux
    )

    mcux_add_source(
        BASE_PATH ${SdkRootDirPath}/middleware/audio_voice/components/decoders/aac
        SOURCES aac_cci.h
        CORES cm7f cm33f cm33
        TOOLCHAINS armgcc mcux
    )
    mcux_add_library(
        BASE_PATH ${SdkRootDirPath}/middleware/audio_voice/components/decoders/aac
        LIBS libs/cm7f/armgcc/release/libaac.a
        CORES cm7f
        TOOLCHAINS armgcc mcux
    )

    mcux_add_library(
        BASE_PATH ${SdkRootDirPath}/middleware/audio_voice/components/decoders/aac
        LIBS libs/cm33f/armgcc/release/libaac.a
        CORES cm33f cm33
        TOOLCHAINS armgcc mcux
    )
endif()