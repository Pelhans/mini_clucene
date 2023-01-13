PROJECT (mini_clucene)

#Rules for version:
#MAJOR and MINOR versions are purely political (tracks JLucene compatibility)
#REVISION version MUST be revised if the headers or compatibility change
#PATCH should be 0 unless a patch is made that doesn't affect the public signature (i.e. clients don't need to re-compile).
SET(CLUCENE_VERSION_MAJOR "2")
SET(CLUCENE_VERSION_MINOR "3")
SET(CLUCENE_VERSION_REVISION "3")
SET(CLUCENE_VERSION_PATCH "4")

# SOVERSION information
#Must be incremented for releases if the api is not backwards compatible
SET(CLUCENE_SOVERSION "1")

MATH(EXPR CLUCENE_INT_VERSION "(${CLUCENE_VERSION_MAJOR} * 1000000) + (${CLUCENE_VERSION_MINOR} * 10000) + (${CLUCENE_VERSION_REVISION} * 100) + (${CLUCENE_VERSION_PATCH} * 1)" )
SET(CLUCENE_VERSION "${CLUCENE_VERSION_MAJOR}.${CLUCENE_VERSION_MINOR}.${CLUCENE_VERSION_REVISION}.${CLUCENE_VERSION_PATCH}")

#CMake 2.6+ is recommended to an improved Boost module
CMAKE_MINIMUM_REQUIRED(VERSION 2.4.0 FATAL_ERROR)


#now write out our configuration....
CONFIGURE_FILE(${mini_clucene_SOURCE_DIR}/shared/clucene-config.h.cmake ${mini_clucene_BINARY_DIR}/shared/clucene-config.h)
CONFIGURE_FILE(${mini_clucene_SOURCE_DIR}/shared/_clucene-config.h.cmake ${mini_clucene_BINARY_DIR}/shared/_clucene-config.h)

#ADD_SUBDIRECTORY (src/shared)