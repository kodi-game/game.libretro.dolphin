cmake_minimum_required(VERSION 3.5)
project(game.libretro.dolphin)

list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR})

find_package(Kodi REQUIRED)
find_library(DOLPHIN_LIB NAMES dolphin_libretro${CMAKE_SHARED_LIBRARY_SUFFIX} PATH_SUFFIXES libretro)

set(DOLPHIN_CUSTOM_BINARY ${DOLPHIN_LIB}
    ${PROJECT_NAME}${CMAKE_SHARED_LIBRARY_SUFFIX})

build_addon(${PROJECT_NAME} DOLPHIN "")

include(CPack)
