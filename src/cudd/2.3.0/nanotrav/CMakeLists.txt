add_library(nanotrav OBJECT
    bnet.c
    chkMterm.c
    main.c
    ntr.c
    ntrBddTest.c
    ntrHeap.c
    ntrMflow.c
    ntrZddTest.c
    ucbqsort.c
    bnet.h
    ntr.h
    )

target_include_directories(nanotrav
    PUBLIC
    ${CMAKE_CURRENT_LIST_DIR}/../util
    ${CMAKE_CURRENT_LIST_DIR}/../st
    ${CMAKE_CURRENT_LIST_DIR}/../dddmp
    ${CMAKE_CURRENT_LIST_DIR}/../cudd
    ${CMAKE_CURRENT_LIST_DIR}/../mtr
    )
