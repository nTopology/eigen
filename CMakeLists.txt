#EIGEN3

add_library(eigen3 INTERFACE)

target_include_directories(eigen3 INTERFACE .)

if(WIN32)
    target_link_libraries(eigen3 INTERFACE mkl thirdparty)
    target_compile_definitions(eigen3 INTERFACE
        EIGEN_USE_MKL_ALL
    )
elseif(UNIX)
  target_link_libraries(eigen3 INTERFACE Threads::Threads)
endif()
