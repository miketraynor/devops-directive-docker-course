.PHONY: build
build:
	docker build --tag my-scratch-image .

# Have to authenticate to dockerhub and create repo first:
# https://docs.docker.com/engine/reference/commandline/login/
.PHONY: push-dockerhub
push-dockerhub:
	docker tag my-scratch-image mfmcgolf/mfmcrepo1
	docker push mfmcgolf/mfmcrepo1

#	docker push mfmcgolf/mfmcrepo1:tagname

	docker tag my-scratch-image mfmcgolf/mfmcrepo1:scratch-123
	docker push mfmcgolf/mfmcrepo1:scratch-123

# Have to authenticate to ghcr.io first
# https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-container-registry#authenticating-to-the-container-registry
.PHONY: push-github-packages
push-github-packages:
	docker tag my-scratch-image ghcr.io/miketraynor/my-scratch-image # defaults to latest
	docker push ghcr.io/miketraynor/my-scratch-image

	docker tag my-scratch-image ghcr.io/miketraynor/my-scratch-image:abc-456
	docker push ghcr.io/miketraynor/my-scratch-image:abc-456
