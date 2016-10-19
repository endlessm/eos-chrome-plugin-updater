pkglibexec_SCRIPTS = \
	eos-chrome-plugin-update

dist_pkglibexec_SCRIPTS = \
	eos-chrome-plugin-update-http \
	eos-chrome-plugin-update-upstream \
	eos-chrome-plugin-update-cros

eos-chrome-plugin-update: eos-chrome-plugin-update.in
	@sed -e "s|\@pkglibexecdir\@|$(pkglibexecdir)|" \
	     -e "s|\@sysconfdir\@|$(sysconfdir)|" $< > $@

networkscriptdir = $(sysconfdir)/NetworkManager/dispatcher.d
dist_networkscript_DATA = 50-eos-chrome-plugin-update-nm

eos-chrome-plugin-update.service: eos-chrome-plugin-update.service.in
	@sed -e "s|\@pkglibexecdir\@|$(pkglibexecdir)|" $< > $@
systemdsystemunit_DATA = eos-chrome-plugin-update.service

install-data-hook:
	chmod +x $(DESTDIR)$(sysconfdir)/NetworkManager/dispatcher.d/50-eos-chrome-plugin-update-nm

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
