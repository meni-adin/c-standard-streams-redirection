set(TARGET_NAME mdn_standard_streams_redirection_test)

include(GoogleTest)

set(TARGET_SOURCES
    "standard_streams_redirection_test.cpp"
)

add_executable(${TARGET_NAME}
    ${TARGET_SOURCES}
)

target_link_libraries(${TARGET_NAME}
    GTest::gmock
    mdn_standard_streams_redirection
    mdn_gtest_extension
)

cmake_language(CALL ${PROJECT_NAME}_set_target_cpp_compiler_flags ${TARGET_NAME})
gtest_discover_tests(${TARGET_NAME})
