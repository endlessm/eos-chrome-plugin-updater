AC_PREREQ([2.63])
AC_INIT([eos-chrome-plugin-updater], [1.0.0], [cosimo@endlessm.com], [eos-chrome-plugin-updater], [http://www.endlessm.com/])
AC_CONFIG_HEADER([config.h])
AC_CONFIG_MACRO_DIR([m4])

AM_INIT_AUTOMAKE([1.11 -Wno-portability foreign no-define tar-ustar no-dist-gzip dist-xz])
AM_MAINTAINER_MODE([enable])
AM_SILENT_RULES([yes])

PKG_PROG_PKG_CONFIG

# systemd
AC_SUBST([systemdsystemunitdir], [$($PKG_CONFIG --variable=systemdsystemunitdir systemd)])

# optionally disable integration with Network Manager (on ifup events)
AC_MSG_CHECKING([whether to enable the integration with Network Manager])
AC_ARG_ENABLE(nm-integration,
              AC_HELP_STRING([--enable-nm-integration],
                             [Enable integration with Network Manager [default=yes]]),
              [enable_nm_integration="$enableval"],
              [enable_nm_integration="yes"])

AC_MSG_RESULT([$enable_nm_integration])
AM_CONDITIONAL([ENABLE_NM_INTEGRATION],[test "x$enable_nm_integration" = "xyes"])

AC_CONFIG_FILES([
Makefile
])
AC_OUTPUT

echo "
    Endless Chrome plugin updater $VERSION
"
