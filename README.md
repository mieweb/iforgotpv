# iforgotpv

Did you forget to run pv on a long running command? iforgotpv to the rescue!

## Description

\`iforgotpv\` is a bash script that allows you to monitor the progress of a running process that's reading from or writing to a file. It's particularly useful when you've started a long-running command and wish you had used \`pv\` (Pipe Viewer) to monitor its progress.

## Features

- Displays progress percentage, current position, total size, transfer rate, and estimated time of arrival (ETA)
- Shows start and end times of the monitored process
- Works with any process ID and file descriptor
- Easy to use with minimal setup

## Installation

### For Debian-based systems (using apt):

\```bash
sudo apt update
sudo apt install iforgotpv
\```

### For Red Hat-based systems (using yum):

\```bash
sudo yum update
sudo yum install iforgotpv
\```

## Usage

\```
iforgotpv <pid> [fd] [interval]
\```

- \`pid\`: Process ID of the command you want to monitor
- \`fd\`: File descriptor (optional, defaults to 1 for stdout)
- \`interval\`: Update interval in seconds (optional, defaults to 1)

### Examples

1. Monitor a process with PID 1234, updating every second:
   \```
   iforgotpv 1234
   \```

2. Monitor a process with PID 5678, file descriptor 3, updating every 5 seconds:
   \```
   iforgotpv 5678 3 5
   \```

3. List file descriptors for a process:
   \```
   iforgotpv 1234
   \```

## Output

The script displays a single-line, continuously updating progress bar with the following information:

- Percentage complete
- Current position / Total size
- Transfer rate
- Estimated time of arrival (ETA)

It also shows the start time when the script begins and the end time when the monitored process completes.

## Notes

- This script requires root privileges or appropriate permissions to access /proc filesystem information for the target process.
- The script will exit when the monitored process completes or if it encounters an error.

## License

[MIT License](https://opensource.org/licenses/MIT)
Credit: https://claude.ai/chat/a27ea613-ddf2-4d5e-9a72-3ca896e49f37

## Contributing

Contributions, issues, and feature requests are welcome! Feel free to check [issues page](https://github.com/yourusername/iforgotpv/issues).

## Show your support

Give a ⭐️ if this project helped you!

