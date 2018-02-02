add_library(cuddobj OBJECT
    cuddObj.cc
    cuddObj.hh
    )

target_include_directories(cuddobj
    PUBLIC
    # ${CMAKE_CURRENT_LIST_DIR}
    ${CMAKE_CURRENT_LIST_DIR}/../cudd
    ${CMAKE_CURRENT_LIST_DIR}/../mtr
    ${CMAKE_CURRENT_LIST_DIR}/../util
    )
