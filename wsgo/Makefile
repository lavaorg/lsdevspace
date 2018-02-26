

all: 


wk:
	go install github.com/lavaorg/ninep

build:
	go install -tags httpstats github.com/lavaorg/warp9/ninep
	go install github.com/lavaorg/warp9/warp9
	go install github.com/lavaorg/warp9/warpsrv
	go install github.com/lavaorg/warp9/servers/...
	go install github.com/lavaorg/warp9/cmd/...
	go install github.com/lavaorg/warp9/tools/...

test:
	go test -v -benchmem -timeout 600s github.com/lavaorg/ninep 

docs:
	godoc -http :9090&

wsinit:
	mkdir -p src

wsclean:
	@rm -rf bin pkg lib
wsnuke:
	@rm -rf bin pkg lib src

wspopulate:
	go get github.com/lavaorg/warp9/ninep
	
gitstatus:
	cd src/github.com/lavaorg/ninep; git status -s
