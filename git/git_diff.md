# Diff different files across commits

For background, I'm trying to diff two different files across different commits. Apparently a file was moved or changed but broke the link within git's understanding. So to git, I'm diffing to unrelated files across two different commits. 

The command looks like:

`git diff <revision1>:<file_1> <revision_2>:<file_2>`

Straightforward enough.
