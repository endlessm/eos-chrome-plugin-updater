dist_pkglibexec_SCRIPTS = eos-pepflash-update

networkscriptdir = $(sysconfdir)/network/if-up.d
dist_networkscript_DATA = eos-pepflash-update-nm

eos-pepflash-update.service: eos-pepflash-update.service.in
	@sed -e "s|\@pkglibexecdir\@|$(pkglibexecdir)|" $< > $@
systemdsystemunit_DATA = eos-pepflash-update.service

install-data-hook:
	chmod +x $(DESTDIR)$(sysconfdir)/network/if-up.d/eos-pepflash-update-nm

EXTRA_DIST = eos-pepflash-update.service.in
CLEANFILES = eos-pepflash-update.service

MAINTAINERCLEANFILES = \
	$(GITIGNORE_MAINTAINERCLEANFILES_TOPLEVEL) \
	$(GITIGNORE_MAINTAINERCLEANFILES_MAKEFILE_IN) \
	$(GITIGNORE_MAINTAINERCLEANFILES_M4_LIBTOOL)

-include $(top_srcdir)/git.mk
