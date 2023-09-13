# watssec-sel4-manifest

Follow the steps to make this work:

Sync the required repos

```
$ mkdir watssec-sel4 && cd watssec-sel4
$ repo init -u https://github.com/watssec/watssec-sel4-manifest.git
$ repo sync
```
Start the docker

```
# append this to shell config file
$ alias container="make -C ./docker user HOST_DIR=$(pwd)"
$ container
```

Build the project

File structure layout

```
- build
- docker
- easy-settings.cmake
- griddle (alias)
- init-build.sh (alias)
- /kernel
- /projects
- /tools
```

Under the root dir, create a build folder.

```
# In build folder
$ ./init-build.sh -DPLATFORM=x86_64 -DSIMULATION=TRUE 
# In build folder
$ ninja

```
## Verification

Verification related file structure layout

```
- HOL4
- l4v
- polyml
- graph-refine
- isabelle 
```

l4v contains most of the proofs, details can be found in [here](https://github.com/seL4/l4v/tree/master)

In order to make isabelle here work, following configs are required:

```
$ isabelle components -I
$ isabelle components -a
```
