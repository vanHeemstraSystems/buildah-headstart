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

I can happen that errors are shown after above instruction. Instead of trying to fix them simple do the following:

```
$ podman machine stop
```

Followed by:

```
$ podman machine stop
```

A few improvements may be mentioned when you have run above command, such as:

```
This machine is currently configured in rootless mode. If your containers require root permissions (e.g. ports < 1024), or if you run into compatibility issues with non-podman clients, you can switch using the following command: 

$ podman machine set --rootful
```

And/or:

```
The system helper service is not installed; the default Docker API socket address can't be used by podman. If yoiu like to install it run the following command:

$ sudo /usr/local/Cellar/podman/4.0.2/bin/podman-mac-helper install
```

And/or:

```
You can still connect to Docker API clients by setting DOCKER_HOST using the following command in your terminal session:

$ export DOCKER_HOST='unix://Users/willemvanheemstra/.local/share/containers/podman/machine/podman-machine-default/podman.sock'
```

You should at least see:

```
Machine "podman-machine-default" started successfully
```

You can then verify the installation information using:

```
$ podman info
```

More advanced information can be found [here](https://github.com/containers/podman/blob/main/docs/tutorials/mac_experimental.md).
