cmake_minimum_required(VERSION 2.8.12.2)

set(CMAKE_INCLUDE_CURRENT_DIR ON)

set(TESTSOURCES
  test11.c
)

add_executable(paltest_duplicatehandle_test11
  ${TESTSOURCES}
)

add_dependencies(paltest_duplicatehandle_test11 CoreClrPal)

target_link_libraries(paltest_duplicatehandle_test11
  pthread
  m
  CoreClrPal
)


set(HELPERSOURCES
  childprocess.c
)

add_executable(paltest_duplicatehandle_test11_child
  ${HELPERSOURCES}
)

add_dependencies(paltest_duplicatehandle_test11_child CoreClrPal)

target_link_libraries(paltest_duplicatehandle_test11_child
  pthread
  m
  CoreClrPal
)
