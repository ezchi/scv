add_library(dddmp OBJECT
    dddmpBinary.c
    dddmpConvert.c
    dddmpDbg.c
    dddmpDdNode.c
    dddmpDump.c
    )

target_include_directories(dddmp
    PUBLIC
    ${CMAKE_CURRENT_SOURCE_DIR}
    ${CMAKE_CURRENT_LIST_DIR}/../util
    ${CMAKE_CURRENT_LIST_DIR}/../cudd
    ${CMAKE_CURRENT_LIST_DIR}/../mtr
    )
