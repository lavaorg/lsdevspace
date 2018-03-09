

help:
	@echo Make targets:
	@echo make build -- build entire repo
	@echo make test  -- test packages
	@echo make docs  -- run godoc -http in background
	@echo make wsint -- init the build env
	@echo make wsclean -- clean build env of buildable artifacts. src is safe
	@echo make wsnuke  -- delete all build and src
	@echo make wspop   -- populate src from git repo
	@echo make gitstatus -- run gitstatus over repo
	@echo 
	@echo

wk:
	go install github.com/lavaorg/ninep

build:
	go install github.com/lavaorg/lrt/...
	go install -tags httpstats github.com/lavaorg/warp/warp9
	go install github.com/lavaorg/warp/nspace
	go install github.com/lavaorg/warp/warpsrv
	go install github.com/lavaorg/warp/servers/...
	go install github.com/lavaorg/warp/cmd/...
	go install github.com/lavaorg/warp/tools/...

test:
	go test -v -benchmem -timeout 600s github.com/lavaorg/warp/warp9

docs:
	godoc -http :9090&

wsinit:
	mkdir -p src
	go get github.com/lavaorg/lrt
	go get github.com/lavaorg/warp

wsclean:
	@rm -rf bin pkg lib
wsnuke:
	@rm -rf bin pkg lib src

wspop:
	go get github.com/lavaorg/warp/
	
gitstatus:
	cd src/github.com/lavaorg/warp; git status -s
