AC_PREREQ([2.63])
AC_INIT([parmigene], [1.0], [gabriele.sales@unipd.it])
AC_CONFIG_SRCDIR([src/mi.c])
AC_CONFIG_HEADERS([src/config.h])

# Setup R config
: ${R_HOME=`R RHOME`}
if test -z "${R_HOME}"; then
  echo "could not determine R_HOME"
  exit 1
fi
CC=`"${R_HOME}/bin/R" CMD config CC`
CFLAGS=`"${R_HOME}/bin/R" CMD config CFLAGS`
CPPFLAGS=`"${R_HOME}/bin/R" CMD config CPPFLAGS`

# Checks for programs.
AC_PROG_CC
AC_PROG_CC_C99

# Checks for libraries.
AC_CHECK_LIB([m],[cos])

# Checks for header files.
AC_CHECK_HEADERS([float.h stdlib.h string.h])

# Checks for typedefs, structures, and compiler characteristics.
AC_C_CONST
AC_OPENMP

# Checks for functions
AC_CHECK_FUNC([rand_r])


AC_CONFIG_FILES([
	src/Makevars
	R/zzz.R
])
AC_OUTPUT
