cmake_minimum_required(VERSION 3.22)
project(ForbiddenEngine)

# Set C++ Standard
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Windows Only
if(NOT WIN32)
    message(FATAL_ERROR "Forbidden Engine only supports Windows PC")
endif()

# Add subdirectories for each phase
add_subdirectory(Phase1_EnhancedEditor)
add_subdirectory(Phase2_BuildSystem)
add_subdirectory(Phase3_Physics)
add_subdirectory(Phase5_Animation)
add_subdirectory(Phase6_Rendering)
add_subdirectory(Phase8_Scripting)
add_subdirectory(Phase9_VisualEditor)

# Main FE Library
add_library(ForbiddenEngine INTERFACE)

# Include directories
target_include_directories(ForbiddenEngine INTERFACE 
    ${CMAKE_CURRENT_SOURCE_DIR}/include
)

message(STATUS "Forbidden Engine - Windows PC Game Development Platform")
message(STATUS "Build Configuration: ${CMAKE_BUILD_TYPE}")
