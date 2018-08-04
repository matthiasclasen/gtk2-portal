dbus_built_sources = xdg-desktop-portal-dbus.c xdg-desktop-portal-dbus.h
BUILT_SOURCES = $(dbus_built_sources)
CLEANFILES = $(dbus_built_sources)

$(dbus_built_sources):
	$(AM_V_GEN) $(GDBUS_CODEGEN)                    \
	--interface-prefix org.freedesktop.impl.portal. \
	--c-namespace XdpImpl                           \
	--generate-c-code xdg-desktop-portal-dbus   \
	$(DESKTOP_PORTAL_INTERFACES_DIR)/org.freedesktop.impl.portal.Request.xml \
	$(DESKTOP_PORTAL_INTERFACES_DIR)/org.freedesktop.impl.portal.FileChooser.xml \
	$(NULL)

libexec_PROGRAMS = \
	xdg-desktop-portal-gtk2 \
	$(NULL)

xdg_desktop_portal_gtk2_SOURCES = \
	portal.c            \
	request.h                           \
	request.c                           \
	filechooser.h                       \
	filechooser.c                       \
	$(dbus_built_sources)			\
	$(NULL)

xdg_desktop_portal_gtk2_LDADD = $(BASE_LIBS) $(GTK_LIBS) $(GTK_X11_LIBS)
xdg_desktop_portal_gtk2_CFLAGS = $(BASE_CFLAGS) $(GTK_CFLAGS) $(GTK_X11_CFLAGS)
xdg_desktop_portal_gtk2_CPPFLAGS = \
	-I$(top_srcdir)                             \
	-I$(top_builddir)                           \
	$(NULL)

portaldir = $(datadir)/xdg-desktop-portal/portals
portal_DATA = a.portal
