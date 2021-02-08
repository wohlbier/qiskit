# Building images

```
# root needs the http proxy set.
jgwohlbier@jgwohlbier-VirtualBox:~/devel/lolcow$ cat /etc/environment
PATH="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games"

#jgw
export http_proxy=${http_proxy}
export https_proxy=${https_proxy}
```

```
# login to remote using generated token
singularity remote login --tokenfile sylabs-token.txt

# make a sandbox from a Singularity def
sudo singularity build --sandbox qiskit qiskit.def
# make the sif from the directory
sudo singularity build qiskit.sif qiskit
singularity run qiskit.sif
```

# Running containers

```
scp qiskit.sif remote.host:
projects
# interactively
interact -p GPU-AI --gres=gpu:volta16:1
singularity shell --nv qiskit.sif
singularity exec --nv qiskit.sif bash_script.sh
```
