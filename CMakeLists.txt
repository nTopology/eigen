#EIGEN3

add_library(eigen3 INTERFACE)

target_include_directories(eigen3 INTERFACE .)

if(WIN32)
    target_link_libraries(eigen3 INTERFACE mkl thirdparty)
    target_compile_definitions(eigen3 INTERFACE
        EIGEN_USE_MKL_ALL
        _ENABLE_EXTENDED_ALIGNED_STORAGE # needed since Visual Studio 15.8, hopefully can remove soon
    )
elseif(UNIX)
  target_link_libraries(eigen3 INTERFACE Threads::Threads)
endif()
