
cmake_minimum_required(VERSION 3.2 FATAL_ERROR)

#find_package(PythonLibs REQUIRED)

include_directories(${PYTHON_INCLUDE_DIR})
include_directories(${XACC_ROOT}/include/pybind11/include)

set (CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -fno-strict-aliasing -O2 -g -pipe -Werror=format-security -Wp,-D_FORTIFY_SOURCE=2 -Wformat -fexceptions -fstack-protector-strong --param=ssp-buffer-size=4 -grecord-gcc-switches -m64 -mtune=generic -D_GNU_SOURCE -fPIC -fwrapv")
if(APPLE)
   set(CMAKE_SHARED_LIBRARY_SUFFIX ".so")
endif(APPLE)

add_library(pyxaccvqebayesopt SHARED xacc-vqe-bayesopt-py.cpp)

set_target_properties(pyxaccvqebayesopt PROPERTIES PREFIX "")

if(APPLE)
   set_target_properties(pyxaccvqebayesopt PROPERTIES INSTALL_RPATH "@loader_path/lib")
   set_target_properties(pyxaccvqebayesopt PROPERTIES LINK_FLAGS "-undefined dynamic_lookup")
else()
   set_target_properties(pyxaccvqebayesopt PROPERTIES INSTALL_RPATH "$ORIGIN/lib")
   set_target_properties(pyxaccvqebayesopt PROPERTIES LINK_FLAGS "-shared")
endif()

install(TARGETS pyxaccvqebayesopt DESTINATION ${CMAKE_INSTALL_PREFIX})
