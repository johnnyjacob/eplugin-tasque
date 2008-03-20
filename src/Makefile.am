INCLUDES =					\
	-I$(top_srcdir)				\
	$(EVOLUTION_MAIL_CFLAGS)

INCLUDES += 	-DDBUS_API_SUBJECT_TO_CHANGE=1		\
		-DDBUS_VERSION=$(DBUS_VERSION)          \
		$(NMN_CFLAGS)

@EVO_PLUGIN_RULE@

plugin_DATA = org-gnome-evolution-tasque.eplug
plugin_LTLIBRARIES = liborg-gnome-evolution-tasque.la

liborg_gnome_evolution_tasque_la_SOURCES = tasque.c
liborg_gnome_evolution_tasque_la_LDFLAGS = 	\
	-module -avoid-version

liborg_gnome_evolution_tasque_la_LDFLAGS += $(NMN_LIBS)

BUILT_SOURCES = $(plugin_DATA)

CLEANFILES = $(BUILT_SOURCES)

DISTCLEANFILES = $(schema_DATA)

EXTRA_DIST = 					\
	org-gnome-evolution-tasque.eplug.xml

