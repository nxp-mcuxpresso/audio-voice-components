if (CONFIG_MCUX_COMPONENT_middleware.audio_voice.components.opus)
    mcux_add_include(
        BASE_PATH ${SdkRootDirPath}/middleware/audio_voice/components/opus
        INCLUDES celt
                 include
                 silk
                 silk/fixed
                 src
    )

    mcux_add_source(
        BASE_PATH ${SdkRootDirPath}/middleware/audio_voice/components/opus
        SOURCES celt/*.c
                celt/*.h
                include/*.h
                silk/*.c
                silk/*.h
                silk/fixed/*.c
                silk/fixed/*.h
                src/*.c
                src/*.h
    )

    mcux_add_configuration(
        CC "-DHAVE_CONFIG_H"
    )
endif()