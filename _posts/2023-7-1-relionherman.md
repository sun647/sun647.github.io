---
title: 'How to run relion on Herman cluster?'
date: 2023-07-01
permalink: /posts/blog-post-11/
tags:
  - relion
  - HPC
  - script
---
I'm sharing a SLURM submission script that's tailored for running RELION on Herman cluster. While an interactive session can be helpful for initial testing, debugging, and code troubleshooting, it's recommended to utilize the full potential of the cluster by submitting jobs through the SLURM system using the sbatch command.   

I noticed that when we transfer our data to the /hpcscratch, we have to manually update the time stamp of the copied files with   
```
touch -m -a file
```
  
Because all the files in the scratch folder longer than 7 days will be purged automatically. I have also added an email notification function to the submission script. It will automatically send me an email if the job fails or when it is finished. Please feel free to email me if you have any questions.   

run_submission.script
```
#!/bin/bash
#SBATCH --job-name=Class3D/job001/
#SBATCH --ntasks=5
#SBATCH --cpus-per-task=6
#SBATCH --error=Class3D/job001/run.err
#SBATCH --output=Class3D/job001/run.out
#SBATCH --nodes=4
#SBATCH --time=7-00:00:00
#SBATCH --gres=gpu:4
#SBATCH --mail-type=END,FAIL
#SBATCH --mail-user=csun@lji.org
module load cmake
module load mpi/openmpi-x86_64
PATH=$PATH:/mnt/saphire-staging/staging/Software/relion4/relion/build_hermanv3/bin

mpirun -n 5 `which relion_refine_mpi` --o Class3D/job001/run --i particles.star --ref ref.mrc --firstiter_cc --ini_high 6 --dont_combine_weights_via_disc --pool 3 --pad 2  --ctf --iter 25 --tau2_fudge 4 --particle_diameter 300 --K 3 --flatten_solvent --zero_mask --solvent_mask cryosparc_P30_J589_000_volume_mask_refine.mrc --oversampling 1 --healpix_order 3 --offset_range 5 --offset_step 2 --sym C1 --norm --scale  --j 6 --gpu ""  --pipeline_control Class3D/job001/
```
