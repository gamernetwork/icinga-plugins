# check_git_sync

Checks two git repos are in sync.

Credentials can be passed in as part of the URL. Or use ssh keys for the Icinga user.

## Examples

### Icinga commands

```
define command{
  command_name    check_git_sync
  command_line    $USER1$/check_git_sync -m "$ARG1$" -s "$ARG2$"
}
```

### Icinga `check_command`

`check_command check_git_sync!git@github.com:myorg/myrepo.git!git@git:myrepo`
