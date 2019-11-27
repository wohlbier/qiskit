NB: root needs the http proxy set.

jgwohlbier@jgwohlbier-VirtualBox:~/devel/lolcow$ cat /etc/environment
PATH="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games"

#jgw
export http_proxy=http://proxy.sei.cmu.edu:8080/
export https_proxy=http://proxy.sei.cmu.edu:8080/


# login to remote using generated token
singularity remote login --tokenfile sylabs-token.txt

# make a sandbox from a Singularity def
sudo singularity build test.sif test.def
singularity run test.sif