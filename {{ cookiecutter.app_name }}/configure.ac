# configure.ac

# Process this file with autoconf to produce a configure script.
AC_INIT([{{ cookiecutter.main }}], [{{ cookiecutter.version }}], [{{ cookiecutter.email }}],
        [{{ cookiecutter.main }}], [{{ cookiecutter.site }}])

# Force autoconf to be at least this version number:
AC_PREREQ([2.68])

# Put autotools auxiliary files in a subdir, so they don't clutter top dir:
AC_CONFIG_AUX_DIR([build-aux])

# The modern autotools convention is that you should use an “m4” subdirectory
# for internal “m4” files, instead of the default aclocal.m4.
#AC_CONFIG_MACRO_DIR([m4])

# Enable "automake" to simplify creating makefiles:
AM_INIT_AUTOMAKE([1.11 -Wall -Werror])

# Checks for programs.
AC_PROG_CC
AC_PROG_CC_C_O

PKG_PROG_PKG_CONFIG
#CFLAGS = `pkg-config --cflags libavutil libavformat libswscale libavcodec`
#LDLIBS = `pkg-config --libs libavutil libavformat libswscale libavcodec`
PKG_CHECK_MODULES(FFMPEG, [libavutil libavformat libswscale libavcodec])

AC_SUBST(FFMPEG_CFLAGS)
AC_SUBST(FFMPEG_LIBS)

AC_CONFIG_FILES([
    Makefile
    {{ cookiecutter.src }}/Makefile
])
AC_OUTPUT

AC_MSG_RESULT(
[
-------------------------------------------------
${PACKAGE_NAME} Version ${PACKAGE_VERSION}
Prefix: '${prefix}'
CC: '${CC}'
CFLAGS: '${CFLAGS}'
FFMPEG_CFLAGS: '${FFMPEG_CFLAGS}'
FFMPEG_LIBS: '${FFMPEG_LIBS}'
Package features:
Async Execution: ${async_exec}
Now type 'make @<:@<target>@:>@'
where the optional <target> is:
all
- build all binaries
install
- install everything
--------------------------------------------------
])
