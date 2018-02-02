add_library(util OBJECT
    cpu_stats.c
    cpu_time.c
    datalimit.c
    getopt.c
    pathsearch.c
    pipefork.c
    prtime.c
    ptime.c
    restart.c
    safe_mem.c
    strsav.c
    stub.c
    texpand.c
    tmpfile.c
    )

target_include_directories(util
    PUBLIC
    ${CMAKE_CURRENT_SOURCE_DIR}
    )
