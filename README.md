# bb
**b**ash **b**ackup

A simple and universal script for creating and restoring backups with archive verification after creation and disk space check before deploying the backup.

```bash
user:~$ ./backup.sh -h

Usage:
  -c --create     Create a backup
  -r --restore    Restore the latest backup
Create options:
  -s    Source directory to backup
  -b    Backup directory
  -v    Verify backup after creation
Restore options:
  -b    Backup directory
  -t    Target directory to restore
  -p    Target partition to restore (for space check)
Examples:
  ./backup.sh -c                       # Create backup in the default directory
  ./backup.sh -c -v                    # Verify backup after creation
  ./backup.sh -c -s /path/to/source    # Create backup of a specific directory
  ./backup.sh -c -b /path/to/backup    # Create backup in a specific directory
  ./backup.sh -c -s /path/to/source -b /path/to/backup
  ./backup.sh -c -s /path/to/source -b /path/to/backup -v
  ./backup.sh -r                      # Restore the latest backup in the default directory
  ./backup.sh -r -b /path/to/backup   # Restore the latest backup in a specific directory
  ./backup.sh -r -b /path/to/backup -t /path/to/target -p sda1
```

It also allows setting certain parameters through global variables.

```bash
BACKUP_PREFIX=
BACKUP_DIR=
SOURCE_DIR=
TARGET_DIR=
TARGET_PARTITION=
LOG_TO_FILE=  # Default: True
LOG_FILE=     # Default: backup.log
```