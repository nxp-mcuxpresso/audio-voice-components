# Copyright 2024 NXP
# SPDX-License-Identifier: BSD-3-Clause

# Set path varriables
set(NXP_AUDIO_COMPONENTS_DIR ${ZEPHYR_CURRENT_MODULE_DIR})
set(COMPONENT_ASRC_DIR "${NXP_AUDIO_COMPONENTS_DIR}/asrc")
set(COMPONENT_SSRC_DIR "${NXP_AUDIO_COMPONENTS_DIR}/ssrc")
set(COMPONENT_OPUS_DIR "${NXP_AUDIO_COMPONENTS_DIR}/opus")
set(COMPONENT_OPUSFILE_DIR "${NXP_AUDIO_COMPONENTS_DIR}/opusfile")
set(COMPONENT_OPUS_OGG_DIR "${NXP_AUDIO_COMPONENTS_DIR}/ogg")
set(COMPONENT_AAC_DIR "${NXP_AUDIO_COMPONENTS_DIR}/decoders/aac")
set(COMPONENT_FLAC_DIR "${NXP_AUDIO_COMPONENTS_DIR}/decoders/flac")
set(COMPONENT_MP3_DIR "${NXP_AUDIO_COMPONENTS_DIR}/decoders/mp3")
set(COMPONENT_WAV_DIR "${NXP_AUDIO_COMPONENTS_DIR}/decoders/wav")

# TODO: Add validation if enabled floating-point for specific architectures

if(CONFIG_CPU_CORTEX_M33)
    set(PLATFORM_ARCH_CORTEX_M33 TRUE)
    set(LIBRARY_ARCHITECTURE_NAME "cm33f")
endif()

if(CONFIG_CPU_CORTEX_M7)
    set(PLATFORM_ARCH_CORTEX_M7 TRUE)
    set(LIBRARY_ARCHITECTURE_NAME "cm7f")
endif()

# If Redfinch RW612 SOC is used, version with no DSP must be selected
# if(CONFIG_SOC_RW612)
#     set(PLATFORM_ARCH_CORTEX_M33_NO_DSP TRUE)
#     set(LIBRARY_ARCHITECTURE_NAME "cm33f_noDSP")
# endif()

# if(CONFIG_SOC_RW612)
#     set(PLATFORM_ARCH_CORTEX_M33_NO_ASM TRUE)
#     set(LIBRARY_ARCHITECTURE_NAME "cm33f_noASM")
# endif()

if(CONFIG_NXP_AUDIO_VOICE_COMPONENTS_TARGET_DEBUG)
    set(LIBRARY_TARGET_NAME "debug")
else()
    set(LIBRARY_TARGET_NAME "release")
endif()

# ===================================================
# = AAC decoder Component
# ===================================================

if(CONFIG_NXP_AUDIO_VOICE_COMPONENTS_DECODER_AAC)
    message("Including NXP Audio-voice component AAC decoder into the build, target ${LIBRARY_TARGET_NAME}")

    if(NOT (CONFIG_CPU_CORTEX_M7 OR PLATFORM_ARCH_CORTEX_M33 OR PLATFORM_ARCH_CORTEX_M3_NO_DSP))
        message(SEND_ERROR "Unsupported architecture")
    endif()

    zephyr_include_directories(${COMPONENT_AAC_DIR})
    zephyr_library_import(nxp_aac_lib ${COMPONENT_AAC_DIR}/libs/${LIBRARY_ARCHITECTURE_NAME}/armgcc/${LIBRARY_TARGET_NAME}/libaac.a)
endif()

# ===================================================
# = FLAC decoder Component
# ===================================================

if(CONFIG_NXP_AUDIO_VOICE_COMPONENTS_DECODER_FLAC)
    message("Including NXP Audio-voice component FLAC decoder into the build, target ${LIBRARY_TARGET_NAME}")

    if(NOT (CONFIG_CPU_CORTEX_M7 OR PLATFORM_ARCH_CORTEX_M33 OR PLATFORM_ARCH_CORTEX_M3_NO_DSP))
        message(SEND_ERROR "Unsupported architecture")
    endif()

    zephyr_include_directories(${COMPONENT_FLAC_DIR})
    zephyr_library_import(nxp_flac_lib ${COMPONENT_FLAC_DIR}/libs/${LIBRARY_ARCHITECTURE_NAME}/armgcc/${LIBRARY_TARGET_NAME}/libflac.a)
endif()

# ===================================================
# = MP3 decoder Component
# ===================================================

if(CONFIG_NXP_AUDIO_VOICE_COMPONENTS_DECODER_MP3)
    message("Including NXP Audio-voice component MP3 decoder into the build, target ${LIBRARY_TARGET_NAME}")

    if(NOT (CONFIG_CPU_CORTEX_M7 OR PLATFORM_ARCH_CORTEX_M33 OR PLATFORM_ARCH_CORTEX_M3_NO_DSP OR PLATFORM_ARCH_CORTEX_M3_NO_ASM))
        message(SEND_ERROR "Unsupported architecture")
    endif()

    zephyr_include_directories(${COMPONENT_MP3_DIR})
    zephyr_library_import(nxp_mp3_lib ${COMPONENT_MP3_DIR}/libs/${LIBRARY_ARCHITECTURE_NAME}/armgcc/${LIBRARY_TARGET_NAME}/libmp3.a)
endif()

# ===================================================
# = WAV decoder Component
# ===================================================

if(CONFIG_NXP_AUDIO_VOICE_COMPONENTS_DECODER_WAV)
    message("Including NXP Audio-voice component WAV decoder into the build, target ${LIBRARY_TARGET_NAME}")

    if(NOT (CONFIG_CPU_CORTEX_M7 OR PLATFORM_ARCH_CORTEX_M33 OR PLATFORM_ARCH_CORTEX_M3_NO_DSP))
        message(SEND_ERROR "Unsupported architecture")
    endif()

    zephyr_include_directories(${COMPONENT_WAV_DIR})
    zephyr_library_import(nxp_wav_lib ${COMPONENT_WAV_DIR}/libs/${LIBRARY_ARCHITECTURE_NAME}/armgcc/${LIBRARY_TARGET_NAME}/libwav.a)
endif()

# ===================================================
# = ASRC Component
# ===================================================

if(CONFIG_NXP_AUDIO_VOICE_COMPONENTS_ASRC)
    message("Including NXP Audio-voice component ASRC into the build, target ${LIBRARY_TARGET_NAME}")
    message(SEND_ERROR "Not yet implemented. TODO.")
    # if(NOT (CONFIG_CPU_CORTEX_M7))
    #     message(SEND_ERROR "Unsupported architecture")
    # endif()

    # file(GLOB ASRC_SOURCES ${COMPONENT_ASRC_DIR}/src/*.c)
    # zephyr_library_import(nxp_asrc_lib ${COMPONENT_ASRC_DIR}/libs/${LIBRARY_ARCHITECTURE_NAME}/armgcc/${LIBRARY_TARGET_NAME}/libasrc.a)
    # zephyr_include_directories(
    #     ${COMPONENT_ASRC_DIR}/inc
    #     ${COMPONENT_ASRC_DIR}/src
    # )
    # zephyr_library_sources(${ASRC_SOURCES})
endif()

# ===================================================
# = SSRC Component
# ===================================================

if(CONFIG_NXP_AUDIO_VOICE_COMPONENTS_SSRC)
    message("Including NXP Audio-voice component SSRC into the build, target ${LIBRARY_TARGET_NAME}")
    message(SEND_ERROR "Not yet implemented. TODO.")
endif()

# ===================================================
# = OPUS Components
# ===================================================

# if(CONFIG_NXP_AUDIO_VOICE_COMPONENTS_OPUS OR CONFIG_NXP_AUDIO_VOICE_COMPONENTS_OPUS_OGG OR CONFIG_NXP_AUDIO_VOICE_COMPONENTS_OPUSFILE)
#     message("Including NXP Audio-voice component OPUS into the build, target ${LIBRARY_TARGET_NAME}")
#     message(SEND_ERROR "Not yet implemented. TODO.")
# endif()

if(CONFIG_NXP_AUDIO_VOICE_COMPONENTS_OPUS)
    message("Including NXP Audio-voice component OPUS into the build")

    # TODO, make it compatible with Kconfig?
    message(WARNING "OPUS configuration may be found in: audio_voice_components/opus/include/config.h")

    # TODO, create a library target for OPUS
    file(GLOB OPUS_SOURCES_FILES
        ${COMPONENT_OPUS_DIR}/celt/*.c
        ${COMPONENT_OPUS_DIR}/silk/*.c
        ${COMPONENT_OPUS_DIR}/silk/fixed/*.c
        ${COMPONENT_OPUS_DIR}/src/*.c
    )
    zephyr_include_directories(
        ${COMPONENT_OPUS_DIR}/celt
        ${COMPONENT_OPUS_DIR}/include
        ${COMPONENT_OPUS_DIR}/silk
        ${COMPONENT_OPUS_DIR}/silk/fixed
        ${COMPONENT_OPUS_DIR}/src
        )
    zephyr_library_sources(${OPUS_SOURCES_FILES})
    zephyr_compile_definitions("-DDHAVE_CONFIG_H")
    zephyr_library_compile_definitions(OGG_OPUS_DEC)
    zephyr_library_compile_definitions(OPUS_BUILD)
    zephyr_library_compile_definitions(VAR_ARRAYS=1)
    zephyr_library_compile_definitions(FIXED_POINT)
    zephyr_library_compile_definitions(DISABLE_FLOAT_API=1)
    zephyr_library_compile_definitions(ENABLE_ASSERTIONS)
    zephyr_library_compile_definitions(ENABLE_HARDENING)
    zephyr_library_compile_definitions(OP_FIXED_POINT) # TODO ???

    zephyr_library_compile_definitions(HAVE_INTTYPES_H=1)
    zephyr_library_compile_definitions(HAVE_LRINT=1)
    zephyr_library_compile_definitions(HAVE_LRINTF=1)
    zephyr_library_compile_definitions(HAVE_MEMORY_H=1)
    zephyr_library_compile_definitions(HAVE_STDINT_H=1)
    zephyr_library_compile_definitions(HAVE_STDLIB_H=1)
    zephyr_library_compile_definitions(HAVE_STRINGS_H=1)
    zephyr_library_compile_definitions(HAVE_STRING_H=1)
    zephyr_library_compile_definitions(HAVE_SYS_STAT_H=1)
    zephyr_library_compile_definitions(HAVE_SYS_TYPES_H=1)
    zephyr_library_compile_definitions(HAVE_UNISTD_H=1)
    zephyr_library_compile_definitions(STDC_HEADERS=1)

    # Surpress warnings from inside the library regarding implicit convertion from float to double
    zephyr_library_cc_option("-Wno-double-promotion")

endif()

if(CONFIG_NXP_AUDIO_VOICE_COMPONENTS_OPUSFILE)
    message("Including NXP Audio-voice component OPUSfile into the build")

    # TODO, create a library target for OPUSFILE
    file(GLOB OPUSFILE_SOURCES_FILES
        ${COMPONENT_OPUSFILE_DIR}/src/*.c
    )
    zephyr_include_directories(
        ${COMPONENT_OPUSFILE_DIR}/include
    )
    zephyr_library_sources(${OPUSFILE_SOURCES_FILES})
endif()

if(CONFIG_NXP_AUDIO_VOICE_COMPONENTS_OPUS_OGG)
    message("Including NXP Audio-voice component OPUS OGG into the build")

    # TODO, create a library target for OPUSFILE
    file(GLOB OPUS_OGG_SOURCES_FILES
        ${COMPONENT_OPUS_OGG_DIR}/src/*.c
    )
    zephyr_include_directories(
        ${COMPONENT_OPUS_OGG_DIR}/include/ogg
        ${COMPONENT_OPUS_OGG_DIR}/src
    )
    zephyr_library_sources(${OPUS_OGG_SOURCES_FILES})
endif()
