pkglibexec_SCRIPTS = \
	eos-chrome-plugin-update

dist_pkglibexec_SCRIPTS = \
	eos-chrome-plugin-update-intel \
	eos-chrome-plugin-update-arm

eos-chrome-plugin-update: eos-chrome-plugin-update.in
	@sed -e "s|\@pkglibexecdir\@|$(pkglibexecdir)|" $< > $@

networkscriptdir = $(sysconfdir)/network/if-up.d
dist_networkscript_DATA = eos-chrome-plugin-update-nm

eos-chrome-plugin-update.service: eos-chrome-plugin-update.service.in
	@sed -e "s|\@pkglibexecdir\@|$(pkglibexecdir)|" $< > $@
systemdsystemunit_DATA = eos-chrome-plugin-update.service

if ENABLE_NM_INTEGRATION
install-data-hook:
	chmod +x $(DESTDIR)$(sysconfdir)/network/if-up.d/eos-chrome-plugin-update-nm
endif

EXTRA_DIST = \
	eos-chrome-plugin-update.in \
	eos-chrome-plugin-update.service.in

CLEANFILES = \
	eos-chrome-plugin-update \
	eos-chrome-plugin-update.service

MAINTAINERCLEANFILES = \
	$(GITIGNORE_MAINTAINERCLEANFILES_TOPLEVEL) \
	$(GITIGNORE_MAINTAINERCLEANFILES_MAKEFILE_IN) \
	$(GITIGNORE_MAINTAINERCLEANFILES_M4_LIBTOOL)

-include $(top_srcdir)/git.mk
