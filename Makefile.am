AUTOMAKE_OPTIONS = 1.9

SUBDIRS = src doc tests

DEBPACKAGE = `echo $(PACKAGE) | tr '_' '-'`

deb: debian/changelog debian/control debian/rules 
	$(MAKE) dist 
	-rm -r debian-build
	-mkdir debian-build 
	cd debian-build ; \
	cp ../$(PACKAGE)-$(VERSION).tar.gz . ; \
	tar xfvz $(PACKAGE)-$(VERSION).tar.gz ; \
	mv $(PACKAGE)-$(VERSION) $(DEBPACKAGE)-$(VERSION) ; \
	cp -R $(DEBPACKAGE)-$(VERSION) $(DEBPACKAGE)-$(VERSION).orig ; \
	cd $(DEBPACKAGE)-$(VERSION) ; \
	mkdir debian ; \
	cp ../../debian/* debian ; \
	dpkg-buildpackage -rfakeroot $(DEBUILD_OPTIONS) ; \
	cd .. ; \
	$(RM) -r $(DEBPACKAGE)-$(VERSION) $(DEBPACKAGE)-$(VERSION).orig
