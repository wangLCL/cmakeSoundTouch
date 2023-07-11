cmake_minimum_required(VERSION 3.18.1)
project("soun")
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/../app/src/main/jniLibs/${ANDROID_ABI})
set(SOURCE_DIR "soundtouch/source")

file(GLOB SOURCE_FILES "${SOURCE_DIR}/*.cpp";"${SOURCE_DIR}/*.h")

add_library(
        soun
        SHARED
        soundtouch-jni.cpp
        ${SOURCE_FILES}
)

find_library(
        log-lib
        log)

target_link_libraries(
        soun
        ${log-lib})

