if (CONFIG_MCUX_COMPONENT_middleware.audio_voice.components.asrc)
    mcux_add_include(
        BASE_PATH ${SdkRootDirPath}/middleware/audio_voice/components/asrc
        INCLUDES inc
        CORES cm7f
        TOOLCHAINS armgcc mcux
    )

    mcux_add_source(
        BASE_PATH ${SdkRootDirPath}/middleware/audio_voice/components/asrc
        SOURCES inc/*.h
        CORES cm7f
        TOOLCHAINS armgcc mcux
    )

    mcux_add_library(
        BASE_PATH ${SdkRootDirPath}/middleware/audio_voice/components/asrc
        LIBS libs/cm7f/armgcc/release/libasrc.a
        CORES cm7f
        TOOLCHAINS armgcc mcux
    )
endif()