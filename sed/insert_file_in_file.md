# Sed - Insert a file into another file

I was updating my notes template to integrate open taskwarrior tasks into the day's tasks and I came across this. 

`r` function appends a file into the output of sed after the match but before any further output. So my command looks like:

`sed -e '/# Tasks/r file1' file2`

which inserts `file1` into `file2` after the `# Tasks` heading. Note that this all happens on stdout, although you can use `-i` to change file2 in place. Also, the `-e` isn't doing anything here, but if you want to apply multiple sed commands you can use `-e` to do it.

As for the Task Warrior part, I did this in a vimscript function but the steps are:
`task export next | jq -r '.[] | .description' | sed 's/^/- \[ \] /' > open_tasks.md`
`sed -e '/# Tasks/r open_tasks.md' templ.md > note.md`
Im writing the tasks to an intermediate file called open_tasks.md, then dumping that into the start of the templates Tasks section. `task export` exports taskwarrior data as json, so I processed it with `jq` and then `sed` to make the markdown contents look the way I wanted.
