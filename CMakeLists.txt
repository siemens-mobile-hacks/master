cmake_minimum_required(VERSION 3.28.2)

include(../sdk/config.cmake)
project(sieelf_master C)

include_directories("../libsie/src/include")
link_libraries(crt crt_helper c gcc)
file(GLOB_RECURSE SOURCES "src/*.c")

add_definitions(-DSWILIB_MODERN -DLANG_EN)

add_executable(Master_ELKA ${SOURCES})
target_sdk_setup(Master_ELKA ELKA)
target_link_directories(Master_ELKA PUBLIC "../libsie/build/lib/ELKA")
target_compile_options(Master_ELKA BEFORE PUBLIC -std=gnu99 -Wall -Werror)

add_executable(Master_NSG ${SOURCES})
target_sdk_setup(Master_NSG NSG)
target_link_directories(Master_NSG PUBLIC "../libsie/build/lib/NSG")
target_compile_options(Master_NSG BEFORE PUBLIC -std=gnu99 -Wall -Werror)

add_executable(Master_SG ${SOURCES})
target_sdk_setup(Master_SG SG)
target_link_directories(Master_SG PUBLIC "../libsie/build/lib/SG")
target_compile_options(Master_SG BEFORE PUBLIC -std=gnu99 -Wall -Werror)
