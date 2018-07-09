cmake_minimum_required (VERSION 3.11)
project(hdlc_analyzer)

# custom CMake Modules are located in the cmake directory.
set(CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake)

include(ExternalAnalyzerSDK)

set(SOURCES 
src/HdlcAnalyzer.cpp
src/HdlcAnalyzer.h
src/HdlcAnalyzerResults.cpp
src/HdlcAnalyzerResults.h
src/HdlcAnalyzerSettings.cpp
src/HdlcAnalyzerSettings.h
src/HdlcSimulationDataGenerator.cpp
src/HdlcSimulationDataGenerator.h
)

add_library(hdlc_analyzer SHARED ${SOURCES})
target_link_libraries(hdlc_analyzer PRIVATE Saleae::AnalyzerSDK)

if(MSVC)
    install(TARGETS hdlc_analyzer RUNTIME DESTINATION "Analyzers")
else()
    install(TARGETS hdlc_analyzer LIBRARY DESTINATION "Analyzers")
endif()

set_post_build_destination(hdlc_analyzer)
