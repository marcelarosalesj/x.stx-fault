NAME ?= "fm-mgr"
DEBMAKE ?= "python"
SRC_PATH ?= "../sources"
all: deps clean
	../../../autodeb/autodeb/autodeb -n $(NAME) -b $(DEBMAKE) -p $(SRC_PATH)
	sudo cp -rf results/*.deb /usr/local/mydebs/
deps:
	while read LINE; do cd ../../"$$LINE"/ubuntu && make clean && make; done < build_deps
clean:
	rm -rf results/
	rm -rf *.tar.gz
	rm -rf $(NAME)-0.0/
	rm -rf *.deb
	rm -rf *.debian.tar.xz
	rm -rf *orig.tar.gz
	rm -rf *.changes
	rm -rf *.dsc
	rm -rf *.build
