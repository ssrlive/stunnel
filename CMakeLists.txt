cmake_minimum_required(VERSION 3.0)
project(stunnel C)

set(CMAKE_C_STANDARD 99)

add_definitions(-DHAVE_CONFIG_H)

include_directories(src linux-cfg)

add_executable(stunnel
        src/client.c
        src/common.h
        src/config.h
        src/cron.c
        src/ctx.c
        src/dhparam.c
        src/env.c
        src/fd.c
        src/file.c
        src/libwrap.c
        src/log.c
        src/network.c
        src/options.c
        src/protocol.c
        src/prototypes.h
        src/pty.c
        src/resolver.c
        src/resources.h
        src/ssl.c
        src/sthreads.c
        src/str.c
        src/stunnel.c
        src/tls.c
        src/ui_unix.c
        #src/ui_win_cli.c
        #src/ui_win_gui.c
        src/verify.c
        src/version.h)

target_link_libraries(stunnel ssl crypto pthread util)
