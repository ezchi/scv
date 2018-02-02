add_library(mnemosyne OBJECT
    mnemalyse.c
    mnemosyne.c
    mnemconf.h
    mnemosyne.h
    )

target_include_directories(mnemosyne
    PUBLIC
    ${CMAKE_CURRENT_LIST_DIR}/../util
)
