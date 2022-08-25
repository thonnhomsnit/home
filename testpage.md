# How to use HPC
-[Submit job via SSH protocal](#submit-job-via-ssh-protocal)
-[Common problems](#common-problems)

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
  - Check the cause
```markdown
$qstat -j jobid 
```
  - Clear error state to rerun '''$qmod -cj jobid'''
```markdown
$qmod -cj jobid
```
2. Error termination without any error massage form LS-DYNA. This problem often occur when disk quota is exceeded (default = 500 GB). This problem can be found by the ('name').e('jobid') file. The only way to fix this problem is clear your directory or submit new issue in hpc.innosoft website.

```markdown
forrtl: Disk quota exceeded
```
