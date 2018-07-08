## script-utils

### About

This repository contains some utility scripts for controlof, and logging from, shell scripts. 

### Dependencies

None.

### Usage

In general, source these files in your scripts.

#### script_logging
**script_logging** contains a few functions for logging from scripts and managing the log files so created:

1. `trim_log_file` - reduces the size of the log file if it exceeds `$MAX_FILE_LINES`, leaving the first to `$BUFFER_LINES` in place;
1. `clean_old_logs` - removes log files in order of age, leaving `$MAX_FILE_COUNT` in place;
1. `write_log` - writes messages to `$LOG_FILE`. Can be used either as a function call, or with a pipe (`|`);
1. `log_message` - allows messages to be written to a file specified in the function call;
1. `update_run` - updates `$RUN_FILE` either with a message or by `touch`.

This script writes files (log, verbose, run) to the following location:
```
LOG_DIR="$HOME/${HIDDEN_LOGS}${USER_REV_URL}
```
`$HIDDEN_LOGS` is defined as . by default; `$USER_REV_URL` is defined as _net.poshboy_ by default. Both of these can be set to values better suited to your deployment.

#### script_ctrl

**script_ctrl** contains three functions for controling script operation:

1. `test_blocked` - test if a scripted it "blocked", i.e. whether it should run or not;
1. `block_script` - block the named script, or the default script name;
1. `release_script` - unblocks a blocked script.

See file for information and default parameter settings, which may all be changed by setting the environment variables appropriately.

### Support and feature requests

Ping me if you have any questions or requests for new features.

### License

Distributed under the MIT License, see LICENSE file in the repository root for more information.
