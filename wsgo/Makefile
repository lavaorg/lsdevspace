

help:
	@echo Make targets:
	@echo make build -- build entire repo
	@echo make arm   -- build entire repo for arm
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
	go install github.com/lavaorg/warp/warp9
	go install github.com/lavaorg/warp/wkit
	go install github.com/lavaorg/warp/tools/...
	go install github.com/lavaorg/dowarp/...

# arm32
ARM= GOARCH=arm GOOS=linux GOARM=7

arm:
	$(ARM) go install github.com/lavaorg/lrt/...
	$(ARM) go install github.com/lavaorg/warp/warp9
	$(ARM) go install github.com/lavaorg/warp/wkit
	$(ARM) go install github.com/lavaorg/warp/tools/...
	$(ARM) go install github.com/lavaorg/dowarp/...

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
	go get github.com/lavaorg/lrt/
	go get github.com/lavaorg/lua/
	go get github.com/lavaorg/dowarp/
	go get github.com/gin-gonic/gin/
	
gitstatus:
	cd src/github.com/lavaorg/warp; git status -s

armdist:
	echo Distribute to raspberry
	
