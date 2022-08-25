# HPC problems

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
