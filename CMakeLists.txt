cmake_minimum_required(VERSION 3.0.0)
project(helloW VERSION 0.1.0)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

# expected behaviour
#set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} /std:c++lastest")

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -DWXUSINGDLL -D__WXOSX_COCOA__ -D__WXMAC__ -D__WXOSX__  -pthread \
-L/opt/wxWidgets/3.1.4/lib -L/usr/local/opt/zlib/lib -pthread /opt/wxWidgets/3.1.4/lib/libwx_osx_cocoau_xrc-3.1.a \
/opt/wxWidgets/3.1.4/lib/libwx_osx_cocoau_qa-3.1.a /opt/wxWidgets/3.1.4/lib/libwx_baseu_net-3.1.a \
/opt/wxWidgets/3.1.4/lib/libwx_osx_cocoau_html-3.1.a /opt/wxWidgets/3.1.4/lib/libwx_osx_cocoau_core-3.1.a \
/opt/wxWidgets/3.1.4/lib/libwx_baseu_xml-3.1.a /opt/wxWidgets/3.1.4/lib/libwx_baseu-3.1.a -lwx_osx_cocoau_core-3.1 \
-lwxjpeg-3.1 -lwxpng-3.1 -lwxtiff-3.1 -framework AudioToolbox -framework WebKit -lwx_baseu-3.1 -lexpat -lz -lpng -lwxregexu-3.1 -liconv \
-framework CoreFoundation -framework Security -framework Carbon -framework Cocoa -framework IOKit -std=c++17")

include(CTest)
enable_testing()

include_directories(
    /opt/wxWidgets/3.1.4/include/wx-3.1
    /opt/wxWidgets/3.1.4/lib/wx/include/osx_cocoa-unicode-static-3.1
)

# find_package(LibXml2 REQUIRED)
# find_package(ZLIB REQUIRED)
# find_package(ICONV MODULE REQUIRED)
# find_package(PNG REQUIRED)

add_executable(helloW helloWorld.cpp)
target_link_directories(helloW PUBLIC
    "/opt/wxWidgets/3.1.4/lib"
)

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)
