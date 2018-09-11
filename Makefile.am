SUBDIRS = src doc tests

deb: debian/changelog debian/control debian/rules 
	$(MAKE) dist 
	-rm -r debian-build
	-mkdir debian-build 
	cd debian-build ; \
	mv ../$(PACKAGE)-$(VERSION).tar.gz $(PACKAGE)_$(VERSION).orig.tar.gz ; \
	tar xfvz $(PACKAGE)_$(VERSION).orig.tar.gz ; \
	cd $(PACKAGE)-$(VERSION) ; \
	mkdir debian ; \
	cp ../../debian/* debian ; \
	dpkg-buildpackage -rfakeroot $(DEBUILD_OPTIONS) ; \
	cd .. ; \
	$(RM) -r $(PACKAGE)-$(VERSION)
