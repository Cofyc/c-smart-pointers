AC_PREREQ([2.60])

AC_INIT([csptr], [1.0], [], [csptr], [franklinmathieu@gmail.com])
AC_CONFIG_SRCDIR([src/mman.c])

LT_PREREQ([2.2.4])
AC_CANONICAL_SYSTEM

AM_INIT_AUTOMAKE([dist-bzip2 no-dist-gzip foreign subdir-objects])
LT_INIT
AC_CONFIG_MACRO_DIR([m4])

AC_PROG_CC
AM_PROG_CC_C_O

AC_PROG_LIBTOOL
AC_PROG_INSTALL
AC_PROG_LN_S

AC_PROG_MAKE_SET
AC_SUBST([LIBTOOL_DEPS])

AC_ARG_WITH([fixed-allocator],
    [AS_HELP_STRING([--with-fixed-allocator], [Always use malloc/free as the allocation system])],
    [AC_DEFINE([SMALLOC_FIXED_ALLOCATOR], [1], [Define if malloc should always be used.])],
    [])

AC_ARG_WITH([malloc-wrapper],
    [AS_HELP_STRING([--with-malloc-wrapper], [Make smart pointers compatible with a pass to free(), and malloc() return a smart pointer.])],
    [AC_DEFINE([SMALLOC_WRAP_MALLOC], [1], [Define if malloc should be wrapped])
     FLAG_WRAP_MALLOC="-Wl,--no-as-needed -ldl"
     AC_SUBST([FLAG_WRAP_MALLOC])
    ],
    [])

AC_CONFIG_HEADERS([src/config.h])
AC_CONFIG_FILES([Makefile])

AC_OUTPUT
