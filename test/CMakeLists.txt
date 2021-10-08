include_directories(../src)
add_executable(testHello
                  testHello.cpp
              )

target_link_libraries(testHello spmv)
target_link_directories(testHello PUBLIC ${CMAKE_CURRENT_BINARY_DIR}/../src)

add_test(NAME testHello_test
         COMMAND testHello
         WORKING_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}
        )
set_tests_properties(testHello_test PROPERTIES
    PASS_REGULAR_EXPRESSION "Hello World"
)
