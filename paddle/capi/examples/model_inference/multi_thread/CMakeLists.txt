project(multi_thread)
cmake_minimum_required(VERSION 2.8)
aux_source_directory(. SRC_LIST)
add_executable(${PROJECT_NAME} ${SRC_LIST})
find_package (Threads)
set_property(TARGET ${PROJECT_NAME} PROPERTY C_STANDARD 99)
target_link_libraries(${PROJECT_NAME} -lpaddle_capi_shared
  ${CMAKE_THREAD_LIBS_INIT})
