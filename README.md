# lo
A perl script to manage ssh login to remote servers.

```
Usage:
lo .                             - show all the mappings
lo ls                            - show all the mappings
lo .show                         - show all the mappings
lo [host]                        - login to the specified host
lo [host] = [user@host.domain]   - map host to the given value
lo [host] is                     - show what host is mapped to
lo [host] auto                   - automate login to host
lo [host] rm|del                 - delete the host mapping
lo [host] tcsh                   - setup host with tcsh and shell scripts
lo [host] com|run [command]      - execute command on host
lo [host] / [command]            - execute command on host
lo [host] ul [local_path] [remote_path]
                                 - upload to the remote host
                                   rsync -aze ssh [local_path] :[remote_path]
lo [host] dl [remote_path] [local_path]
                                 - download from the remote host
                                   rsync -aze ssh :[remote_path] [local_path]
lo [host] ulx [local] [remote]   - same as ul but also delete remote path/file to mirror local
lo [host] dlx [local] [remote]   - same as dl but also delete local path/file to mirror remote
```

