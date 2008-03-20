INCLUDES =					\
	-I$(top_srcdir)				\
	$(EVOLUTION_MAIL_CFLAGS)

INCLUDES += 	-DDBUS_API_SUBJECT_TO_CHANGE=1		\
		-DDBUS_VERSION=$(DBUS_VERSION)          \
		$(NMN_CFLAGS)

%.eplug: %.eplug.in
	sed -e 's|\@PLUGINDIR\@|$(plugindir)|'		\
	-e 's|\@SOEXT\@|$(SOEXT)|'			\
	-e 's|\@GETTEXT_PACKAGE\@|$(GETTEXT_PACKAGE)|'	\
	-e 's|\@LOCALEDIR\@|$(localedir)|' $< > $@

%.eplug.in: %.eplug.xml
	LC_ALL=C $(INTLTOOL_MERGE) -x -u /tmp $< $@

%.error: %.error.xml
	LC_ALL=C $(INTLTOOL_MERGE) -x -u /tmp $< $@

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

