#  This file is a part of SEAPT, Samsung Extended Autotools Project Template

#  Copyright 2012,2013 Samsung R&D Institute Russia
#  All rights reserved.
#
#  Redistribution and use in source and binary forms, with or without
#  modification, are permitted provided that the following conditions are met: 
#
#  1. Redistributions of source code must retain the above copyright notice, this
#     list of conditions and the following disclaimer. 
#  2. Redistributions in binary form must reproduce the above copyright notice,
#     this list of conditions and the following disclaimer in the documentation
#     and/or other materials provided with the distribution.
#
#  THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND
#  ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED
#  WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
#  DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT OWNER OR CONTRIBUTORS BE LIABLE FOR
#  ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES
#  (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES;
#  LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND
#  ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
#  (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS
#  SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

AC_INIT(???, 1.0)
m4_include([common.ac])
# Libtool -version-info
AC_SUBST(INTERFACE_VERSION, [0])
AC_SUBST(REVISION_NUMBER, [$(cd $srcdir && git rev-list HEAD --count)])
AC_SUBST(AGE_NUMBER, [0])

# Check some lib...
#PKG_CHECK_MODULES([ZLIB], [zlib >= 1.2.3])

# Add a feature (not enabled by default)
#AC_ARG_ENABLE([feature],
#    AS_HELP_STRING([--enable-feature], [build with feature])
#)
#AS_IF([test "x$enable_feature" == "xyes"], [
#    ...
#])

# Add a feature (enabled by default)
#AC_ARG_ENABLE([feature],
#    AS_HELP_STRING([--disable-feature], [build without feature])
#)
#AS_IF([test "x$enable_feature" != "xno"], [
#    ...
#])

# Add an optional feature
#AC_ARG_WITH([feature],
#    AS_HELP_STRING([--with-feature], [additionally, build feature]), [
    # Action if true
#], [
    # Action if false    
#])

# Additional tests
#AM_COND_IF([TESTS], [
#    AC_CONFIG_FILES(tests/subdirectory/Makefile
#                    )
#])

# Link with Makefile.am in additional source directories
#AC_CONFIG_FILES(src/subdirectory/Makefile
#                )

AC_OUTPUT

COMMON_PRINT_STATUS
