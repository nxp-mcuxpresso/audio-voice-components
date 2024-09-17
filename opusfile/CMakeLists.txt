if (CONFIG_MCUX_COMPONENT_middleware.audio_voice.components.opusfile)
    mcux_add_include(
        BASE_PATH ${SdkRootDirPath}/middleware/audio_voice/components/opusfile
        INCLUDES include
    )

    mcux_add_source(
        BASE_PATH ${SdkRootDirPath}/middleware/audio_voice/components/opusfile

        SOURCES include/*.h
                src/*.c
    )
endif()