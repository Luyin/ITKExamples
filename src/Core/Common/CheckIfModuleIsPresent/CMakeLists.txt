cmake_minimum_required(VERSION 3.10.2)

project(CheckIfModuleIsPresent)

find_package(ITK REQUIRED)
include(${ITK_USE_FILE})


add_executable(CheckIfModuleIsPresent Code.cxx)
target_link_libraries(CheckIfModuleIsPresent ${ITK_LIBRARIES})

install(TARGETS CheckIfModuleIsPresent
  DESTINATION bin/ITKExamples/Core/Common
  COMPONENT Runtime
  )

install(FILES Code.cxx CMakeLists.txt
  DESTINATION share/ITKExamples/Code/Core/Common/CheckIfModuleIsPresent/
  COMPONENT Code
  )


enable_testing()
add_test(NAME CheckIfModuleIsPresentTest
  COMMAND ${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/CheckIfModuleIsPresent)
