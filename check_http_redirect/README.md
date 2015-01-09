# check_http_redirect

Simple HTTP redirect check. It just checks one level of redirects and will not
follow the redirect. If you need to test multiple redirect levels you need one
check for each level.

Pass in a url, the expected value of the `Location` response and an optional
http status. By default it will expect a 301 Moved Permanently status.

Authentication can be passed in as `-a user:pass`.

## Requirements

You'll need to pip install these libs:

 * docopt
 * requests

## Examples

### Icinga commands

```
define command{
  command_name    check_http_redirect
  command_line    $USER1$/check_http_redirect -I $HOSTADDRESS$ -u $ARG1$ -p $ARG2$ -r $ARG3$ -c $ARG4$
}

define command{
  command_name    check_http_redirect_auth
  command_line    $USER1$/check_http_redirect -I $HOSTADDRESS$ -u $ARG1$ -p $ARG2$ -r $ARG3$ -c $ARG4$ -a $ARG5$:$ARG6$
}
```

### Icinga `check_command`

Verify http to https redirect is happening.

`check_command check_http_redirect!http://foo.example.com!8080!https://foo.example.com/!301`

Verify relative redirect with auth.

`check_command check_http_redirect_auth!https://foo.example.com!443!admin/!302!user!pass`
