
# Serve the site locally.
serve:
	hugo server

# Build the site. Among other things, this populates the public/ folder.
build:
	hugo

# Used by Netlify to build the site.
netlify-build: init-theme build

netlify-deploy-preview: init-theme
	hugo --enableGitInfo --buildFuture -b $(DEPLOY_PRIME_URL)

# Used by Netlify to pull in the theme (plain git-clone of our main repo is not enough).
init-theme:
	git submodule update --init --recursive

# Update the "docsy" Hugo theme.
update-theme: init-theme
	git submodule update --remote
	npm update

.PHONY: \
	init-theme \
	update-theme
