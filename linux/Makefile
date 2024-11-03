TARGET_SYMBOLS := /usr/share/X11/xkb/symbols/us
SOURCE_SYMBOLS := usr-share-X11-xkb-symbols-us
TARGET_RULES := /usr/share/X11/xkb/rules/evdev.xml
SOURCE_RULES := usr-share-X11-xkb-rules-evdev

all: reinstall

install: $(SOURCE_SYMBOLS) $(TARGET_SYMBOLS) $(SOURCE_RULES) $(TARGET_RULES)
	cat $(SOURCE_SYMBOLS) >> $(TARGET_SYMBOLS)
	sed -i "$$(awk '/variantList/{ print NR; exit }' $(TARGET_RULES)) r $(SOURCE_RULES)" $(TARGET_RULES)

uninstall: $(TARGET_SYMBOLS) $(TARGET_RULES)
	sed -i '/ ENTHIUM BEGIN /,/ ENTHIUM END /d' $^

reinstall:
	$(MAKE) uninstall
	$(MAKE) install

.PHONY: all install uninstall reinstall
