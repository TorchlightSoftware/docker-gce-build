# Docker Development Build Scripts

These are some scripts that I've built up while using docker and google cloud.  Others may find them helpful.

These should probably be compiled into some kind of build tool.

# Usage

```bash
./scripts/build # will build the Dockerfile in the current directory named by name/version from package.json
./scripts/start # will start the image with the current name/version from package.json
./scripts/deploy # the image is prefixed with your current GCE project - this will deploy it to GCE
./scripts/restart # restart the image
./scripts/stop # stop the image
./scripts/manual # will start the image with a bash terminal
```

# Install

You should have the `gcloud` cli [already installed](https://cloud.google.com/sdk/downloads), authenticated, and pointed at a project.  `gcloud` will be called by these scripts to determine naming and to run the deploy.

This is more for inspiration than anything, but I suppose if you wanted to you could bring these files in directly like so:

```bash
git clone https://github.com/TorchlightSoftware/docker-gce-build.git scripts
```

Or add it as a submodule to your project:

```bash
git submodule add https://github.com/TorchlightSoftware/docker-gce-build.git scripts
```

The scripts use the version number from package.json in your home directory.  So run NPM init to get one.

```bash
npm init
```
