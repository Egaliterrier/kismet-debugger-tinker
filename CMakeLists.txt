cmake_minimum_required(VERSION 3.18)

project(KismetDebugger)

add_subdirectory(RE-UE4SS)

set(TARGET KismetDebugger)
project(${TARGET})

set(${TARGET}_Sources
        "${CMAKE_CURRENT_SOURCE_DIR}/src/dllmain.cpp"
        "${CMAKE_CURRENT_SOURCE_DIR}/src/KismetDebugger.cpp"
        )

add_library(${TARGET} SHARED ${${TARGET}_Sources})
target_include_directories(${TARGET} PRIVATE "include")
target_link_libraries(${TARGET} PRIVATE ImGui)
target_link_libraries(${TARGET} PUBLIC UE4SS)
