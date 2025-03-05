project(QCSimulator)
aux_source_directory(. SRC_CXX)

add_library(QCSimulator ${SRC_CXX})
set_property(TARGET QCSimulator PROPERTY CUDA_ARCHITECTURES 70)
target_link_libraries(QCSimulator PRIVATE CUDA::cublas)
message(
  STATUS
    "CMAKE_CUDA_IMPLICIT_INCLUDE_DIRECTORIES: ${CMAKE_CUDA_IMPLICIT_INCLUDE_DIRECTORIES}"
)
get_target_property(target_includes QCSimulator INCLUDE_DIRECTORIES)
message(STATUS "QCSimulator include directories: ${target_includes}")
