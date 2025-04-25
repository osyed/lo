# lo
A perl script to manage ssh login to remote servers. Makes ssh and rsync easier.

First setup a mapping:
* lo devbox = myuserid@host1.company.com

Now instead of:
* ssh myuserid@host1.company.com
* lo devbox

To setup auto login using keys instead of password:
* lo devbox auto

To run a command on devbox:
* lo devbox run ls -al

To upload a file or directory to devbox:
* lo devbox ul file.txt
* lo devbox ul file.txt newfile.txt
* lo devbox ul file.txt tmpdir
* lo devbox ul file.txt tmpdir/newfile.txt

To download a file or directory from devbox:
* lo devbox dl file.txt
* lo devbox dl file.txt newfile.txt
* lo devbox dl file.txt tmpdir
* lo devbox dl file.txt tmpdir/newfile.txt


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
lo .keys                         - show all the ~/.ssh/*.pem files and current one in use
lo [host] key [key_file]         - set the key file to use for the specified host
```

## Setup
* wget https://raw.githubusercontent.com/osyed/lo/refs/heads/master/lo
* chmod +x lo
* mv lo ~/bin  # or another directory that is in you path
