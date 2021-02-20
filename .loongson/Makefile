build:
	GOARCH=mips64le make build
	make docker-build DAPR_REGISTRY=loongson DAPR_TAG=1.0.0 TARGET_ARCH=mips64le
	
