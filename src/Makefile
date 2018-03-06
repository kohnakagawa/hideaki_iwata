OUT_DIR=../docs
# modified version of stackoverflow (https://stackoverflow.com/questions/22072773/batch-export-of-org-mode-files-from-the-command-line)
FILES=$(patsubst %.org,$(OUT_DIR)/%.html,$(wildcard *.org))

.PHONY: all clean install-doc

all: install-doc

install-doc: $(FILES)

%.html: %.org
	emacs $< --batch -f org-html-export-to-html --kill

$(OUT_DIR)/%.html: %.html
	install -v -m 644 -t $(OUT_DIR) $<
	rm $<

clean:
	rm $(FILES)
