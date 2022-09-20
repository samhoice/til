# Using ALE with Python in vim

I've been trying to figure out why ALE tools won't work with my python code... It works in one of my projects but not the other. Turns out, it's (as usual with Python) virtualenv's fault. In the project where I have the virtualenv installed with pyenv, it works fine. In the project that uses Pipenv, it doesn't work at all because the linting tools are not in a venv when I start my editor up. My current solution is to create a vim virtualenv with pyenv that I can activate for vim that just has the needed dev tools in it. So far it's:

- black
- pylint
- mypy
- pyright

and their dependencies. I guess if I were using pip-tools I'd know what all their dependencies were...

I should write a blog post about sorting out all the pip related tools in Python.
