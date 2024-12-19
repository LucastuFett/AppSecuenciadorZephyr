# Add the USB MIDI driver module. CMAKE_CURRENT_SOURCE_DIR is 
# the dir containing the sample app's CMakeLists.txt, i.e the 
# repository root dir, which is also the root dir of the
# driver module.
#list(APPEND ZEPHYR_EXTRA_MODULES ${CMAKE_CURRENT_SOURCE_DIR})

cmake_minimum_required(VERSION 3.20.0)

list(APPEND ZEPHYR_EXTRA_MODULES ${CMAKE_CURRENT_SOURCE_DIR}/zephyr-usb-midi)
find_package(Zephyr REQUIRED HINTS $ENV{ZEPHYR_BASE})
project(app LANGUAGES C)

target_sources(app PRIVATE src/main.c)
