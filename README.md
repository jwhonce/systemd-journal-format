# systemd-journal-format

Tool to convert journalctl --output verbose to journalctl --output export

## Use case:
  As a developer, I want to query the docker logging from a given set of sosreport artifacts using journalctl


## Usage:

```sh
  $ cat journalctl_--all_--this-boot_--no-pager_-o_verbose.txt | systemd-journal-reformat >journal.export
  $ cat journal.export | /usr/lib/systemd/systemd-journal-remote -o pmaddocks.journal -
  $ journalctl -D , -u docker.service
```

## Bugs:
 * Most exceptions not related to reading from stdin will cause script to fail.
