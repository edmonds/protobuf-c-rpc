AC_PREREQ(2.60)
AC_INIT([protobuf-c-rpc], [0.1])
AC_CONFIG_SRCDIR([protobuf-c-rpc/protobuf-c-rpc.c])
AC_CONFIG_AUX_DIR([build-aux])
AM_INIT_AUTOMAKE([foreign 1.11 -Wall -Wno-portability silent-rules subdir-objects])
AC_PROG_CC_STDC
AC_USE_SYSTEM_EXTENSIONS
AC_SYS_LARGEFILE
AC_CONFIG_MACRO_DIR([m4])
AM_SILENT_RULES([yes])
LT_INIT

AC_CONFIG_HEADERS(config.h)
AC_CONFIG_FILES([Makefile protobuf-c-rpc/libprotobuf-c-rpc.pc])

AC_CHECK_HEADERS(alloca.h)
AC_CHECK_HEADERS(io.h)
AC_CHECK_HEADERS(malloc.h)
AC_CHECK_HEADERS(sys/poll.h)
AC_CHECK_HEADERS(sys/select.h)
AC_CHECK_HEADERS(sys/uio.h)
AC_CHECK_HEADERS(unistd.h)
AC_CHECK_HEADERS(winsock.h)

PKG_PROG_PKG_CONFIG
if test -n "$PKG_CONFIG"; then
    # Horrible hack for systems where the pkg-config install directory is simply wrong!
    if $PKG_CONFIG --variable=pc_path pkg-config 2>/dev/null | grep -q /libdata/; then
        PKG_INSTALLDIR(['${prefix}/libdata/pkgconfig'])
    else
        PKG_INSTALLDIR
    fi
else
    AC_MSG_ERROR([pkg-config is required!])
fi

PKG_CHECK_MODULES([libprotobuf_c], [libprotobuf-c])
AC_PATH_PROG([PROTOC_C], [protoc-c])

AC_OUTPUT
AC_MSG_RESULT([
    $PACKAGE $VERSION

        CC:                     ${CC}
        CFLAGS:                 ${CFLAGS}
        LDFLAGS:                ${LDFLAGS}
        LIBS:                   ${LIBS}

        prefix:                 ${prefix}
        sysconfdir:             ${sysconfdir}
        libdir:                 ${libdir}
        includedir:             ${includedir}
        pkgconfigdir:           ${pkgconfigdir}
])
