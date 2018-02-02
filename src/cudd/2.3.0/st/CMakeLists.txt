add_library(st OBJECT
    st.c
    st.h
    )

target_include_directories(st
    PUBLIC
    ${CMAKE_CURRENT_LIST_DIR}/../util
)
