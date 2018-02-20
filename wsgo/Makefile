

all: 


wk:
	go install github.com/lavaorg/ninep

build:
	go install github.com/lavaorg/ninep
	go install github.com/lavaorg/ninep/cmd/ufs
	go install github.com/lavaorg/ninep/tools/ls
	go install github.com/lavaorg/ninep/tools/cat

test:
	go test -v -benchmem -timeout 20s github.com/lavaorg/ninep -run ^TestAttachOpenReaddir1

wsinit:
	mkdir -p src

wsclean:
	@rm -rf bin pkg lib
wsnuke:
	@rm -rf bin pkg lib src

gitstatus:
	cd src/github.com/lavaorg/9p; git status -s
