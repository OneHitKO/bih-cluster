# How-To: Connect to High-Memory Nodes

## Prequisites

You have to register with [hpc-gatekeeper@bihealth.de](mailto:hpc-gatekeeper@bihealth.de) for requesting access.

Afterwards, you can connect to the High-Memory using the `highmem` SLURM partition (see below).

## How-To

In the cluster there are four High-memory used which can be used:

```
med-login1:~$ sinfo -p highmem
PARTITION AVAIL  TIMELIMIT  NODES  STATE NODELIST 
highmem      up 14-00:00:0      3   idle med040[1-4] 
```

To connect to one of them, use the below command from login node:
```
med-login1:~$ srun --pty -p highmem bash -i
med0401:~$
```
You can also pick one of the hostnames:

```
med-login1:~$ ssh med0403
med0403:~$
```

After successfull login, you can see that you are in "highmem" queue:

```
med0403:~$ squeue
             JOBID PARTITION     NAME     USER ST       TIME  NODES NODELIST(REASON) 
[...]
               270   highmem     bash holtgrem  R       1:25      1 med0403 

```
