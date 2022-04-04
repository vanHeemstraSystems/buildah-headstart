# 100 - Installation of Podman on MacOS

Based on "Installing packaged versions of Podman" at https://podman.io/getting-started/installation

Podman is a tool for running Linux containers. You can do this from a MacOS desktop as long as you have access to a linux box either running inside of a VM on the host, or available via the network. Podman includes a command, podman machine that automatically manages VM’s.

**Remote Client**
The Mac client is available through [Homebrew](https://brew.sh/):

```
$ brew install podman
```

To start the Podman-managed VM:

```
$ podman machine init
$ podman machine start
```

You can then verify the installation information using:

```
$ podman info
```

More advanced information can be found [here](https://github.com/containers/podman/blob/main/docs/tutorials/mac_experimental.md).
