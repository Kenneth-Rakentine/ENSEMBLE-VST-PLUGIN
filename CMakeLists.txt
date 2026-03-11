cmake_minimum_required(VERSION 3.22)

project(ENSEMBLE VERSION 0.1.0)

# ---- SET YOUR JUCE PATH HERE ----
if(NOT DEFINED JUCE_DIR)
    set(JUCE_DIR "C:/JUCE" CACHE PATH "Path to JUCE framework")
endif()

add_subdirectory(${JUCE_DIR} ${CMAKE_BINARY_DIR}/juce_build)

juce_add_plugin(Ensemble
    COMPANY_NAME "Depattern"
    PLUGIN_MANUFACTURER_CODE Ensm
    PLUGIN_CODE Ensb
    FORMATS VST3 Standalone
    PRODUCT_NAME "ENSEMBLE"
    IS_SYNTH FALSE
    NEEDS_MIDI_INPUT FALSE
    NEEDS_MIDI_OUTPUT FALSE
    IS_MIDI_EFFECT FALSE
    EDITOR_WANTS_KEYBOARD_FOCUS FALSE
    COPY_PLUGIN_AFTER_BUILD FALSE
)

target_sources(Ensemble
    PRIVATE
        Source/PluginProcessor.cpp
        Source/PluginEditor.cpp
)

target_include_directories(Ensemble
    PRIVATE
        Source
        Source/DSP
)

target_link_libraries(Ensemble
    PRIVATE
        juce::juce_audio_utils
        juce::juce_dsp
    PUBLIC
        juce::juce_recommended_config_flags
        juce::juce_recommended_lto_flags
        juce::juce_recommended_warning_flags
)

target_compile_definitions(Ensemble
    PUBLIC
        JUCE_WEB_BROWSER=0
        JUCE_USE_CURL=0
        JUCE_VST3_CAN_REPLACE_VST2=0
        JUCE_DISPLAY_SPLASH_SCREEN=0
        $<$<PLATFORM_ID:Linux>:JUCE_ALSA=0>
)

target_compile_features(Ensemble PRIVATE cxx_std_17)
