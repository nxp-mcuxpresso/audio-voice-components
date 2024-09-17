if (CONFIG_MCUX_COMPONENT_middleware.audio_voice.components.ogg)
    mcux_add_include(
        BASE_PATH ${SdkRootDirPath}/middleware/audio_voice/components/ogg
        INCLUDES src
                 include/ogg
    )

    mcux_add_source(
        BASE_PATH ${SdkRootDirPath}/middleware/audio_voice/components/ogg
        SOURCES include/ogg/*.h
                src/*.c
                src/*.h
    )
endif()