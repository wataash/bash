cmake_minimum_required(VERSION 3.8)
project(bash)

set(CMAKE_VERBOSE_MAKEFILE on)

file(GLOB_RECURSE SRCS "*.c" "*.h")

add_executable(zdummy ${SRCS})
add_custom_target(bash COMMAND cd ${PROJECT_SOURCE_DIR}/build && make)

include_directories(
        include
        lib
        lib/intl
        build/lib/intl
)

add_definitions(
        -DPROGRAM='"bash"'
        -DCONF_HOSTTYPE='"x86_64"'
        -DCONF_OSTYPE='"darwin15.6.0"'
        -DCONF_MACHTYPE='"x86_64-apple-darwin15.6.0"'
        -DCONF_VENDOR='"apple"'
        -DLOCALEDIR='"/Users/wsh/usr/share/locale"'
        -DPACKAGE='"bash"'
        -DSHELL
        -DHAVE_CONFIG_H
        -DMACOSX
)
