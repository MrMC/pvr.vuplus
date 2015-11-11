project(pvr.vuplus)

cmake_minimum_required(VERSION 2.6)

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} ${PROJECT_SOURCE_DIR})

enable_language(CXX)

find_package(mrmc REQUIRED)
find_package(mrmcplatform REQUIRED)
find_package(platform REQUIRED)
find_package(TinyXML REQUIRED)

include_directories(${mrmcplatform_INCLUDE_DIRS}
                    ${platform_INCLUDE_DIRS}
                    ${TINYXML_INCLUDE_DIR}
                    ${MRMC_INCLUDE_DIR})

set(VUPLUS_SOURCES src/client.cpp
                   src/VuData.cpp)

set(DEPLIBS ${mrmcplatform_LIBRARIES}
            ${platform_LIBRARIES}
            ${TINYXML_LIBRARIES})

build_addon(pvr.vuplus VUPLUS DEPLIBS)

include(CPack)
