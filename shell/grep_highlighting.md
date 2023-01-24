# Highlighting output with grep

Looking at log files coming in realtime from a program, I wanted a way to highlight certain keywords without filtering the rest of the logs. Turns out you can do this with grep:

`<run program> | egrep --color "pattern|$"`

This will match `pattern` and highlight it, or match the non-printable end of line character (and presumably highlight it, too). The effect will be to highlight the pattern and print everything.

From:
https://stackoverflow.com/questions/981601/colorized-grep-viewing-the-entire-file-with-highlighted-matches

Alternative with ripgrep:
`<run program> | rg --passthru -e pattern`

Just give more `-e` options for additional matches
