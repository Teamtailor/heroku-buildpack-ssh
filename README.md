# Heroku Buildpack: SSH

Makes it possible to use SSH in a safe way on your dyno.

## Usage

Set `SSH_KEY` and `SSH_KNOWN_HOSTS` variables:

    heroku config:set SSH_KEY="`cat /path/to/id_rsa`"
    heroku config:set SSH_KNOWN_HOSTS="`ssh-keyscan <REMOTE SERVER IP-ADDRESS>`"

You can have more than one remote server ip-address. You can add them by appending to the existing heroku environment variable.

`SSH_KEY` must not require a password to use. Before your application is run the `SSH_KEY` environment variable is unset.

This buildpack should be loaded before any buildpacks requiring access to private repositories.

## Bugs

Please report any bugs to using the [issue tracker](https://github.com/teamtailor/heroku-buildpack-ssh/issues).

Pull requests are welcome.
