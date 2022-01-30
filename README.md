## About

This is a helper script to automate backups using [restic](https://restic.readthedocs.io/en/stable/index.html)

Supports:

- backing up to a local directory
- backing up to a remote sftp server

## How to use

```
cp config.example config
cp excludes.txt.example excludes.txt
cp includes.txt.example includes.txt
$EDITOR config excludes.txt includes.txt
./restic-wrapper
```

### Running from cron

Example root crontab entry:

```
30 3 * * * /path/to/restic-scripts/restic-wrapper
```

## Restore

### Local directory

To restore from local backups, the easiest way is to mount backups

```
restic mount -r /path/to/backup/repo ./restore
```
