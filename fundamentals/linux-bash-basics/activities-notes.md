# Bash Basics — Activities & Notes

## Daily warm-ups
- `pwd`, `ls -la`, `cd` into at least two levels; observe relative vs absolute paths.
- Create/remove files and dirs: `touch`, `mkdir -p`, `rm -r`, `mv`, `cp`.
- Inspect files: `cat`, `less`, `head`, `tail -f`, `wc -l`.
- Permissions: `ls -l` to read bits, `chmod u+x` on a script, `whoami`, `id`.

## Hands-on scripts
- Hello script: print greeting and current date/time. Add executable bit and run via `./hello.sh`.
- Arguments: script that echoes `$0`, `$1`, `$#`, `$@`, and errors if no args.
- Variables & quoting: show difference between `"${var}"` and `${var}` when spaces appear.
- Exit codes: script that runs a command, prints `$?`, and uses `exit 1` on failure path.
- Conditionals: test file existence with `[ -f file ]`, branches for missing/present.
- Loops: `for f in *.log; do ...; done` to count lines or search text.
- Functions: wrap a reusable check (e.g., ensure file exists) and return non-zero on failure.
- Piping and redirection: combine `cat | grep | sort | uniq -c`; practice `>`, `>>`, `2>`, `&>`.
- Cron-style: sketch a `crontab -e` entry and note `PATH` considerations.

## File & text operations
- `grep -R "pattern" .` vs `rg` for speed; note `-n`, `-C2` context flags.
- `find . -type f -name "*.sh" -maxdepth 3 -mtime -1` to locate recent scripts.
- `sed` basics: inline replace with backup `sed -i.bak 's/foo/bar/g' file`.
- `awk` basics: print columns `awk '{print $1, $3}' file`; sum numeric column.
- `xargs` with `find` to run commands safely (`-print0 | xargs -0`).

## Environment & shell comfort
- Profile files: know where `~/.bashrc`, `~/.profile`, `/etc/profile` apply.
- Aliases and functions in `~/.bashrc`; reload with `source ~/.bashrc`.
- `$PATH` inspection and temporary prepending `export PATH="/opt/bin:$PATH"`.
- History search: `history`, `Ctrl+R`, and `HISTCONTROL=ignoredups`.

## Debugging & safety
- Use `set -euo pipefail` atop scripts; add `IFS=$'\n\t'` for safer word splitting.
- Trace execution with `bash -x script.sh` or `set -x` within a block.
- Create a `tmp/` scratch area and avoid running as root; practice `sudo -l`.

## Checklist before moving on
- Can write and run a script with args, flags, and basic validation.
- Comfortable with file/text search using `find`, `grep`/`rg`, `sed`, `awk`.
- Know how to inspect permissions and adjust execute bits.
- Use redirection/pipes confidently and understand exit codes.
