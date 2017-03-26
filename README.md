# Docker/Gcloud Build Scripts

These are some scripts that I've built up while using Docker and Google Cloud.  Others may find them helpful.



# Usage

```bash
./scripts/build # will build the Dockerfile in the current directory named by name/version from package.json
./scripts/start # will start the image with the current name/version from package.json
./scripts/push # the image is prefixed with your current GCE project - this will deploy it to GCE
./scripts/restart # restart the image
./scripts/stop # stop the image
./scripts/manual # will start the image with a bash terminal
```

# Install

You should have the `gcloud` cli [already installed](https://cloud.google.com/sdk/downloads), authenticated, and pointed at a project.  `gcloud` will be called by these scripts to determine naming and to run the deploy.

The scripts use the version number from package.json in your home directory.  So run NPM init to get one.

```bash
npm init
```

You can clone the scripts:

```bash
git clone https://github.com/TorchlightSoftware/docker-gce-build.git scripts
```

Or add them as a submodule to your project:

```bash
git submodule add https://github.com/TorchlightSoftware/docker-gce-build.git scripts
```

You'll probably end up making project specific changes to the `start` and `manual` scripts.  I don't have a good solution for that.  These scripts should probably be turned into some kind of build tool with a config file.  This is just a quick and dirty implementation that works for me.

Feel free to throw out a pull request or issue if you can think of a better way.
