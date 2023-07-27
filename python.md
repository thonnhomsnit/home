# How to use HPC
-[job.sh file preparation](#job.sh-file-preparation)

-[Submit job via SSH protocal](#submit-job-via-ssh-protocal)

-[Common problems](#common-problems)


## job.sh file preparation
The bash script in job.sh file is used as the job configuration for submitting the job in HPC. The job.sh has the certain structure including the null space at the last line of the script as shown

```markdown
#!/bin/bash
#$ -cwd
#$ -v LSTC_LICENSE
#$ -v LSTC_LICENSE_SERVER={ip-address}
#$ -v lstc_s
#$ -v lstc_d
#$ -N {jobname}
#$ -q short.q
#$ -pe orte {cpu-core}

$lstc_d "memory=99999999 ncpu=$NSLOTS i={filename}.k"

```

## Submit job via SSH protocal

1. Enter the password. The **** thingy will not show on the command line interface. But don't worry, you are typing correctly.
2. Get in to your job's directory by using 'cd' command.
```markdown
$cd (your job's directory)
```
3. Optional: You can check the job.sh detail by using 'cat' command before submitting the job.sh file.
```markdown
$cat job.sh 
```
4. Submit the job.sh file by using 'qsub' command.
```markdown
$qsub job.sh 
```
5. If you want to submit another job in other directory, you can use 'cd' again to go back in the home directory and follow the procedure from step 1 to 4.
```markdown
$cd - 
``` 

## Common problems

1. "Eqw" means that the job is waiting in error state. It may caused by temporarily server down.
  - Check the cause by using 
```markdown
$qstat -j jobid 
```
  - Clear error state to rerun
```markdown
$qmod -cj jobid
```
2. Error termination without any error massage form LS-DYNA. This problem often occur when disk quota is exceeded (default = 500 GB). This problem can be found by the ('name').e('jobid') file. The only way to fix this problem is clear your directory or submit new issue in hpc.innosoft website.

```markdown
forrtl: Disk quota exceeded
```
