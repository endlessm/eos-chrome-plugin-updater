AC_PREREQ([2.63])
AC_INIT([eos-chrome-plugin-updater], [1.0.2], [emdev@endlessm.com], [eos-chrome-plugin-updater], [http://www.endlessm.com/])
AC_CONFIG_HEADER([config.h])
AC_CONFIG_MACRO_DIR([m4])

AM_INIT_AUTOMAKE([1.11 -Wno-portability foreign no-define tar-ustar no-dist-gzip dist-xz])
AM_MAINTAINER_MODE([enable])
AM_SILENT_RULES([yes])

PKG_PROG_PKG_CONFIG

# systemd
AC_SUBST([systemdsystemunitdir], [$($PKG_CONFIG --variable=systemdsystemunitdir systemd)])

AC_CONFIG_FILES([
Makefile
])
AC_OUTPUT

echo "
    Endless Chrome plugin updater $VERSION
"
