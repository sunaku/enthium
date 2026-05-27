TARGET_SYMBOLS := /usr/share/X11/xkb/symbols/us
SOURCE_SYMBOLS := usr-share-X11-xkb-symbols-us
TARGET_RULES := /usr/share/X11/xkb/rules/evdev.xml
SOURCE_RULES := usr-share-X11-xkb-rules-evdev
TARGET_LIST := /usr/share/X11/xkb/rules/evdev.lst
SOURCE_LIST := usr-share-X11-xkb-rules-evdev.lst

all: reinstall

install: $(SOURCE_SYMBOLS) $(TARGET_SYMBOLS) $(SOURCE_RULES) $(TARGET_RULES)
	cat $(SOURCE_SYMBOLS) >> $(TARGET_SYMBOLS)
	sed -i "$$(awk '/<description>English \(US\)</ { en_US=1 }; en_US && /<variantList>/ { print NR; exit }' $(TARGET_RULES)) r $(SOURCE_RULES)" $(TARGET_RULES)
	sed -i "$$(awk '/^! variant/ { print NR; exit }' $(TARGET_LIST)) r $(SOURCE_LIST)" $(TARGET_LIST)

uninstall: $(TARGET_SYMBOLS) $(TARGET_RULES)
	sed -i '/ ENTHIUM BEGIN /,/ ENTHIUM END /d' $^
	sed -i '/enthium/d' $(TARGET_LIST)

reinstall:
	$(MAKE) uninstall
	$(MAKE) install

.PHONY: all install uninstall reinstall
