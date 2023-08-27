# Simple Tripwire-like POSIX shell script

Simple Shell script to create a list of all files and their kast mocification dates to compare and
determine what has changed on the system.


The Simple Tripwire Shell Script is a POSIX-compliant shell script designed to provide basic intrusion detection capabilities by monitoring changes to specified files and directories. It helps detect unauthorized modifications to critical system files, helping to maintain the integrity and security of your system.

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Prerequisites](#prerequisites)
- [Usage](#usage)
- [Configuration](#configuration)
- [Customization](#customization)
- [Cron Job](#cron-job)
- [Reporting](#reporting)
- [Contributing](#contributing)
- [License](#license)

## Introduction

**Depends heavily on the `find` command**

Tripwire is a well-known security tool used to detect changes to files and directories on a system. This Simple Tripwire Shell Script provides a lightweight alternative to full-fledged Tripwire installations, offering a straightforward way to monitor important files for any unauthorized changes.

## Features

- Monitors specified files and directories for modifications.
- Generates checksums for monitored files and stores them in a secure database file.
- Compares current checksums with stored checksums to detect changes.
- Notifies users about detected changes via email.

## Prerequisites

- POSIX-compliant shell (e.g., Bash).
- `md5sum` or `sha256sum` utility, depending on your preference.
- `mail` command for email notifications.

## Usage

1. Clone or download this repository to your system.
2. Ensure the script has execute permissions: `chmod +x tripwire.sh`.
3. Edit the script's configuration section as needed (see [Configuration](#configuration)).
4. Run the script manually: `./tripwire.sh`.
5. Alternatively, set up a cron job to run the script at desired intervals (see [Cron Job](#cron-job)).

## Configuration

In the script, you will find a configuration section that contains variables to be customized:

- `MONITORED_DIRS`: List of directories to be monitored.
- `REPORT_EMAIL`: Email address where notifications will be sent.
- `CHECKSUM_ALGORITHM`: Choose between `md5sum` or `sha256sum` for checksum generation.

## Customization

You can customize this script to fit your needs:

- Add or remove directories and files from the `MONITORED_DIRS` list.
- Modify the notification message to include more details about the changes detected.
- Enhance the reporting functionality by integrating with other notification mechanisms.

## Cron Job

To automate the monitoring process, you can set up a cron job:

1. Open the crontab configuration: `crontab -e`.
2. Add a line to schedule the script. For example, to run the script every day at 2:00 AM:
   ```
   0 2 * * * /path/to/tripwire.sh
   ```
3. Save and exit the crontab editor.

## Reporting

When changes are detected, the script sends an email to the address specified in `REPORT_EMAIL` containing information about the changes detected. Make sure your system is set up to send emails using the `mail` command.

## Contributing

Contributions to this project are welcome. Feel free to fork the repository, make improvements, and submit pull requests.

## License

This project is licensed under the [MIT License](LICENSE).

---

**Note:** This script provides basic intrusion detection capabilities. For more advanced security needs, consider using a dedicated intrusion detection system like Tripwire or other comprehensive security solutions.


---

Developed and Documentation By: **Raymond C. TURNER**

Last Updated: Sunday 27th August 2023 @ 15:22 BST
