# Scope IOWait Plugin

The Scope IOWait plugin is a GO application that uses [`iostat`](https://linux.die.net/man/1/iostat) to provide **host-level** CPU IO wait or idle metrics in the [Weave Scope](https://github.com/weaveworks/scope) UI.

<img src="imgs/iowait.png" width="800" alt="Scope IOWait Plugin screenshot" align="center">

## How to Run Scope IOWait Plugin

* Using a pre-built Docker image

```
docker pull weaveworks-plugins/scope-iowait:latest
docker run --rm --ti \ 
			 --net=host \
			 -v /var/run/scope/plugins:/var/run/scope/plugins \
			 --name weaveworks-plugins-scope-iowait weaveworks-plugins/scope-iowait:latest
```

* Recompiling an image

```
git clone git@github.com:weaveworks-plugins/scope-iowait.git
cd scope-iowait; make;
```

**Note** If Scope IOWait plugin has been registered by Scope, you will see it in the list of `PLUGINS` in the bottom right of the UI (see the rectangle in the above figure).
The measured value is showed in the *STATUS* section (see the circle in the above figure).
