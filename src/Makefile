COMPILER = gcc
FILESYSTEM_FILES = main.c

build: $(FILESYSTEM_FILES)
	$(COMPILER) $(FILESYSTEM_FILES) -o main `pkg-config fuse3 --cflags --libs`

clean:
	rm main
