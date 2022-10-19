# node-base

## Usage

### Base commands

```bash
# Runs the command inside an ephemeral container using the app service described in the docker-compose file as a base (use the --root flag if the command should be run as root)
$ dbin/run [--root] <command>

# Rebuild the image after any changes to the dockerfile
$ dbin/build

# Remove all containers and their volumes (WARNING any cache or files not stored in the filesystem will be deleted)
$ dbin/dispose

# Moves the target folder contents to the root folder and deletes the target folder
# it also renames this file to INSTRUCTIONS.md
$ dbin/mvroot <target>

# Appends a RUN command to the base image, useful to install new packages
$ dbin/chimg <command>
```

### Aliases

```bash
# Creates a new <name> file in dbin to alias the <command> inside the docker container (use the --root flag if the command should be run as root)
$ dbin/mkalias [--root] <name> <command>

# Opens a new terminal in the project folder (use the --root flag if the shell should assume the root user)
$ dbin/shell [--root]

# Runs npm in the project folder
$ dbin/npm

# Runs npx in the project folder
$ dbin/npx

# Runs yarn in the project folder
$ dbin/yarn
```

### Helpers

```bash
# Adds dbin folder to the PATH only for the current terminal session.
$ source dbin/local-env

# After using this command you can use the any script inside the dbin folder without the dbin/ prefix
```

## Examples

### React Native with Expo

```bash
# Clone this repository
$ git clone --depth=1 https://github.com/brunohcastro/node-base.git my-awesome-expo-app

# Install expo-cli
$ dbin/npm install -g expo-cli

# Create an alias for using the local expo
$ dbin/mkalias expo expo

# Create a new expo app
$ dbin/expo init my-app

# Move the contents of the my-app folder over to the root repo folder
$ dbin/mvroot my-app

# Start the application
$ dbin/expo start
```

### NextJS

```bash
# Clone this repository
$ git clone --depth=1 https://github.com/brunohcastro/node-base.git my-awesome-nextjs-app

# Create the application
$ dbin/npx create-next-app my-app

# Move it to the root folder
$ dbin/mvroot my-app

# Start the application in development mode
$ dbin/npm run dev
```

### Create T3 App

```bash
# Clone this repository
$ git clone --depth=1 https://github.com/brunohcastro/node-base.git my-awesome-t3-app

# (optional) Remove the .git folder to let the cli create a brand new git repo
$ rm -rf ./.git

# Create the application
$ dbin/npx create-t3-app my-app

# Move it to the root folder
$ dbin/mvroot my-app

# Start the application in development mode
$ dbin/npm run dev
```
