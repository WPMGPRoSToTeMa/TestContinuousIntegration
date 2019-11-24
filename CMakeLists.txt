project(TestContinuousIntegration)

add_library(${PROJECT_NAME} MODULE Main.cxx)

set_target_properties(${PROJECT_NAME} PROPERTIES PREFIX "")
foreach(config ${CMAKE_CONFIGURATION_TYPES})
    string(TOUPPER ${config} config)
    set_target_properties(${PROJECT_NAME} PROPERTIES RUNTIME_OUTPUT_DIRECTORY_${config} "${CMAKE_BINARY_DIR}/bin")
endforeach()