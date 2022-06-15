# node-base

## Usage

### Base commands

```bash
# Runs the command inside an ephemeral container using the app service described in the docker-compose file as a base
$ dbin/exec <command>

# Rebuild the image after any changes to the dockerfile
$ dbin/build

# Remove all containers and their volumes (WARNING any cache or files not stored in the filesystem will be deleted)
$ dbin/dispose

# Moves the target folder contents to the root folder and deletes the target folder
# it also renames this file to INSTRUCTIONS.md
$ dbin/mvroot <target>
```

### Aliases

```bash
# Creates a new file in dbin to alias that command inside the docker container
$ dbin/mkalias

# Runs npm in the project folder
$ dbin/npm

# Runs npx in the project folder
$ dbin/npx

# Runs yarn in the project folder
$ dbin/yarn
```

## Examples

### React Native with Expo

```bash
$ dbin/npm install -g expo-cli
$ dbin/mkalias expo
$ dbin/expo init my-app
$ dbin/mvroot my-app
$ dbin/expo start
```

### NextJS

```bash
$ dbin/npx create-next-app my-app
$ dbin/mvroot my-app
$ dbin/yarn dev
```