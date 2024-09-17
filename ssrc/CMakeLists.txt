if (CONFIG_MCUX_COMPONENT_middleware.audio_voice.components.ssrc)
    mcux_add_include(
        BASE_PATH ${SdkRootDirPath}/middleware/audio_voice/components/ssrc
        INCLUDES .
        CORES cm33f cm33 cm7f
        TOOLCHAINS armgcc iar mcux
    )

    mcux_add_source(
        BASE_PATH ${SdkRootDirPath}/middleware/audio_voice/components/ssrc
        SOURCES SSRC.h
                LVC_Types.h
        CORES cm33f cm33 cm7f
        TOOLCHAINS armgcc iar mcux
    )

    mcux_add_library(
        BASE_PATH ${SdkRootDirPath}/middleware/audio_voice/components/ssrc
        LIBS libs/cm7f/armgcc/release/libssrc.a
        CORES cm7f
        TOOLCHAINS armgcc mcux
    )

    mcux_add_library(
        BASE_PATH ${SdkRootDirPath}/middleware/audio_voice/components/ssrc
        LIBS libs/cm33f/armgcc/release/libssrc.a
        CORES cm33f cm33
        TOOLCHAINS armgcc mcux
    )

    mcux_add_library(
        BASE_PATH ${SdkRootDirPath}/middleware/audio_voice/components/ssrc
        LIBS libs/cm7f/iar/release/libssrc.a
        CORES cm7f
        TOOLCHAINS iar
    )

    mcux_add_library(
        BASE_PATH ${SdkRootDirPath}/middleware/audio_voice/components/ssrc
        LIBS libs/cm33f/iar/release/libssrc.a
        CORES cm33f cm33
        TOOLCHAINS iar
    )
endif()