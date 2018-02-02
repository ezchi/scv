add_library(mtr OBJECT
    mtrBasic.c
    mtrGroup.c
    mtr.h
    )

target_include_directories(mtr
    PUBLIC
    ${CMAKE_CURRENT_LIST_DIR}/../util
)
