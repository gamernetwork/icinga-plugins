# check_linux_io_scheduler

Make sure no one had change the IO scheduler for a device.

## Examples

### Icinga command

```
define command {
  command_name    check_remote_linux_io_scheduler
  command_line    $USER1$/check_by_ssh --skip-stderr -H $HOSTADDRESS$ -l nagios -C "/usr/lib/nagios/plugins/check_linux_io_scheduler $ARG1$ $ARG2$"
}
```

### Icinga `check_command`

`check_command check_remote_linux_io_scheduler!sda!deadline`
