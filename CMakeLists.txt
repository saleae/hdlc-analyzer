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

add_analyzer_plugin(hdlc_analyzer SOURCES ${SOURCES})
