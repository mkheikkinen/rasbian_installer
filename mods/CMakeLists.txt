project(rameplayer-utils C)
cmake_minimum_required(VERSION 2.8)

set(CMAKE_INSTALL_PREFIX /usr)
set(CMAKE_INSTALL_RPATH /opt/vc/lib)


find_package(PkgConfig)
pkg_check_modules(FT freetype2)

add_definitions( -std=gnu99 )

#set(COMPILE_DEFINITIONS -Werror -Wall -O3)

include_directories(${FT_INCLUDE_DIRS})
include_directories(/usr/include/freetype2/)

SET(CMAKE_EXE_LINKER_FLAGS "-v -lfreetype -lm")

add_subdirectory(librameutil)
add_subdirectory(ramefbcp)
add_subdirectory(rametext)
add_subdirectory(rameclock)
