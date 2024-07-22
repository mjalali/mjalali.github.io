---
layout: post
title:  Tips to use with Slurm and remote server!
date:   2024-07-20 16:40:16
description: This is my experience with working remote servers in the CSE department at the Chinese University of Hong Kong (CUHK).
tags: CUHK remote-server slurm
categories: tips
---

### Outlines:
<ul>
    <li>Adding your Public Key to the server</li>
    <li>Adding essential variables to ~/.bashrc</li>
    <li>Installing conda on Big data storage</li>
    <li>Changing the vscode installing path for extensions</li>
    <li>Scheduling a job with tmux and slurm</li>
</ul>

### Adding your Public Key to the server
If you don't want to enter your password each time you connect to the server you can do the following steps:
follow [this link](https://linuxhandbook.com/add-ssh-public-key-to-server/).
(linux9 is an example)
```shell
ssh-keygen -t rsa
ssh-copy-id -i ~/.ssh/id_rsa.pub <user_name>@linux9
```
### Adding essential variables to ~/.bashrc
You can add these variables to `~/.bashrc` to prevent exceeding the memory limit. 
**Note**: Remember to change <user_name> to your username!
```shell
# Torch and Python
export TORCH_HOME=/research/.../<user_name>/.cache/
export PIP_CACHE_DIR=/research/.../<user_name>/.cache/
export PYTHONUSERBASE=/research/.../<user_name>/.cache/python
export XDG_CACHE_HOME=/research/.../<user_name>/.cache/

# Slurm Confs
export SLURM_CONF=/opt1/slurm/gpu-slurm.conf
```
### Installing conda on Big data storage
You need to install conda in order to work with different python versions on the server and the `~` directory space
is limited. You can follow [this link](https://docs.anaconda.com/miniconda/)
1. go to your big data storage directory (sth like `/research/d2/.../<user_name>`)
2. `mkdir -p /research/.../<user_name>/miniconda3`
3. `wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O /research/.../<user_name>/miniconda3/miniconda.sh`
4. `bash /research/.../<user_name>/miniconda3/miniconda.sh`
5. `rm -rf /research/.../<user_name>/miniconda3/miniconda.sh`
6. `./miniconda3/bin/conda init bash`

### Changing the vscode installing path for extensions
Due to the limited space in the home directory, if you want to install some VS code extensions, you need to change
the installing path.
You can see [this link](https://stackoverflow.com/questions/71063547/change-default-extensions-location-for-remote-development-in-vs-code) for more information or just follow these steps:
1. Go to the settings
2. Search `Remote.SSH: Server Install Path` in the settings.
3. add the name of the server as the `key` and `/research/d2/rshr/<user_name>/` as the path. (For example)

### Scheduling a job with tmux and slurm
1. First make a tmux session
2. Allocate the gpu using slurm commands. (Follow [this link](https://i.cse.cuhk.edu.hk/technical/gpgpu-hpc-service/slurm/))
3. Run your code!
4. Detach from tmux using (cntrl + b + d)
5. You can attach again using `tmux a` command.


**If you had any question, you can just contact me!**