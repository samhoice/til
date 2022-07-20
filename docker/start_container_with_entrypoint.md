# Starting a container without running it's command

Sometimes you need to debug a docker container without running the command that the container sets. For instance, if the command is failing and the container is exiting with an error, or if the command is a task that runs and not a daemon that just executes. In this case you can do:

`docker run --interactive --tty --entrypoint=/bin/bash test_container:v0.0.8`

It's `--entrypoint` that's doing the work here, redefining the container entrypoint (in this case to a bash shell). I used this to debug python virtualenvs on a container that wouldn't start. Once I figured out what was wrong, I could fix the dockerfile and rebuild.
