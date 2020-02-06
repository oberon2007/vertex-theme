themedir       = $(datadir)/themes/Vertex
themedarkdir   = $(datadir)/themes/Vertex-Dark
themelightdir  = $(datadir)/themes/Vertex-Light

ithemedir      = $(DESTDIR)$(themedir)
ithemedarkdir  = $(DESTDIR)$(themedarkdir)
ithemelightdir = $(DESTDIR)$(themelightdir)


install-exec-hook:

install-data-local:

if ENABLE_PLANK

	$(MKDIR_P) $(ithemedir)
	cp -R $(srcdir)/Vertex-Plank/. $(ithemedir)/plank

if ENABLE_DARK
	$(MKDIR_P) $(ithemedarkdir)
	cp -R $(srcdir)/Vertex-Plank/. $(ithemedarkdir)/plank
endif # ENABLE_DARKER

if ENABLE_LIGHT
	$(MKDIR_P) $(ithemelightdir)
	cp -R $(srcdir)/Vertex-Plank/. $(ithemelightdir)/plank
endif # ENABLE_DARK
endif # ENABLE_PLANK


uninstall-local:

EXTRA_DIST = \
	Chrome \
	Firefox \
	Ubuntu-Software-Center \
	Vertex_alt_metacity \
	Vertex-Plank
