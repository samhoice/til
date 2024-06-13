# Just

I like having a task runner that runs independently of `npm` or `python manage.py` or whatever toolchain I'm actually using. Recently I've been using the `just` task runner. I'd started using fabric with python, but there were definitely things that bothered me about it. It's handy when you want to run something on a remote, but it's much more like writing code than just a few shell commands.  I find `just` to be simple in the way `make` was intended but actually much more usable.


A couple of things I like about just

- No phony targets (although `make` seems more relaxed about this now)
- Easy to do dependencies (like `make`)
- Can easily drop into bash (or python!) for more complex steps

Reflecting on it here, I think the thing I like most is having a task runner where I can list common tasks which I can write in a composable way. Make is fine, but this is a tiny bit easier and that's enough.


## Some recipes:

Running `just` by itelf can list commands

```justfile
default:
    @just --list --justfile {{justfile()}}
```

## Links

[Github Link](https://github.com/casey/just)
[XDG Directories](https://github.com/casey/just?tab=readme-ov-file#xdg-directories1230)
