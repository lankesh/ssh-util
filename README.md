# Description
This project is designed to help you manage your ssh accounts
- You can use this tool to connect to your servers.
- Only two things are required:
    - pem file
    - ssh command per server
- The logic to connect to your server is handled by this utility
- The utility will also set the right permissions for the pem file if it's not already set to `400`

# Requirements
- This utility expects `ssh` is installed
- This utility expects PEM file is in following format:
    - `<server-name>@<ssh-username>@<ip-address>.pem`
    - Where
        - `<server-name>` is the user friendly name of the remote server
        - `<ssh-username>` is the username that is used to connect the remote server
        - `<ip-address>` is the IP address of the remote server
    - For E.g. If I have a remote server named `achme-prod` and it is a `ubuntu` server with IP Address `127.0.0.1`, then I would name my PEM file as follows:
        - `achme-company-prod@ubuntu@127.0.0.1.pem`

# Notes
- You can put this in your execution `$PATH` for ease of use
    - To do that alter the `$PATH` variable
    - For mac I added this to my `~/.zshrc` profile:
        ```
        export PATH="/Users/sslankesh/work/ss-commands:$PATH"
        ```
- Delete the example pem file (`achme-company-prod@ubuntu@127.0.0.1.pem`) from `pem` directory

# Limitations
- The `<ssh-username>` cannot have `@` & space in it
    - For E.g. `ubuntu@user` is not allowed
    - For E.g. `ubuntu user` is not allowed
    - For E.g. `ubuntuuser` is allowed
- The `<server-name>` cannot have `@` in it
    - For E.g. `achme-company@prod` is not allowed
    - For E.g. `achme-company-prod` is allowed
- This utility works with `IPv4 addresses` only
- This utility works only in `mac` and `linux` environments
- This utility works only with `zsh` and `bash` shells
- This utility works only with `pem` files
