AC_PREREQ([2.63])

AC_INIT([xdg-desktop-portal-gtk2],[0.1])

AC_PROG_CC
AM_PROG_CC_C_O
AC_DISABLE_STATIC

LT_PREREQ([2.2.6])
LT_INIT([disable-static])

AC_CONFIG_SRCDIR([portal.c])
AC_CONFIG_HEADERS([config.h])
AC_CONFIG_MACRO_DIR([m4])
AM_INIT_AUTOMAKE([1.11 no-define no-dist-gzip dist-xz tar-ustar foreign subdir-objects])
AC_PROG_SED

# Enable silent rules is available
AM_SILENT_RULES([yes])
AM_MAINTAINER_MODE([enable])

PKG_PROG_PKG_CONFIG([0.24])

AC_SUBST([DESKTOP_PORTAL_INTERFACES_DIR], [`$PKG_CONFIG --variable=interfaces_dir xdg-desktop-portal`])
AC_SUBST([DBUS_INTERFACES_DIR], [`$PKG_CONFIG --variable=interfaces_dir dbus-1`])
AC_SUBST([GDBUS_CODEGEN], [`$PKG_CONFIG --variable gdbus_codegen gio-2.0`])
AC_SUBST([GLIB_COMPILE_RESOURCES], [`$PKG_CONFIG --variable glib_compile_resources gio-2.0`])

PKG_CHECK_MODULES(GTK, [xdg-desktop-portal glib-2.0 >= 2.44 gio-unix-2.0 gtk+-2.0 >= 2.24])
AC_SUBST(GTK_CFLAGS)
AC_SUBST(GTK_LIBS)

AC_CONFIG_FILES([
Makefile
])
AC_OUTPUT

