# check_svn_sync

Checks master and slave subversion repos are in sync.

If authentication is required, credentials are expected to he be the same on
master and slave.

## Examples

### Icinga commands

```
define command{
  command_name    check_svn_sync
  command_line    $USER1$/check_svn_sync -m $ARG1$ -s $ARG2$ -u $ARG3$ -p $ARG4$
}
```

### Icinga `check_command`

`check_command check_svn_sync!svn://master.svn.example.com/repo!svn://slave.svn.example.com/repo!nagios!0000`
