cmake_minimum_required(VERSION 3.2 FATAL_ERROR)
project(CityTrafficSimulator++ VERSION 0.1 LANGUAGES CXX)
include("cmake/commonconf.cmake")

option(BUILD_SHARED_LIBS "Build Shared Libraries" ON)
option(ENABLE_SCRIPTING "Enable Lua Scripting" OFF)
option(ENABLE_TESTING "Enable Testing" ON)


# External 3rd party libs that we include
add_subdirectory(ext/tinyxml2)

# Targets that we develop
add_subdirectory(cts-core)
add_subdirectory(cts-gui)

if(ENABLE_SCRIPTING)
  add_subdirectory(ext/lua-5.3)
  add_subdirectory(cts-lua)
endif()

add_subdirectory(cts++)
