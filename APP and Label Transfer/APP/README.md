There are multiple variants of the same script:

If the script name contains the "_parallel" modifier, parallel computations will be performed; otherwise, sequential computations will be used.
If the script name contains the "_fixed_param" modifier, it will use fixed intrinsic parameters. Conversely, if the script name contains the "_dynamic_param" modifier, parameters will be computed at runtime.

Run examples:

````
# Size of the smallest population expected to be detected
min_cluster_size=30  

# Total number of dimensions in the dataset
ndim=10  

# Number of parallel computation threads
workers_count=4  

# 2D histogram bin size (without auto-adjustment)
h=0.01  

# Parameter for Gaussian histogram smoothing
sigma=5  

# Step size along the y-axis for decision boundary computation
dq=0.02  

# Free parameter controlling the influence of the "y0-gravity potential" on clustering
beta=0.1  

# Analogous to beta but without auto-adjustment
q2=0.1  

# Maximum absolute value of the decision boundary derivative with respect to x
max_dj=5

fn_in='../test_data/PHA0026.csv'

python variation_parallel_from_cmd_fixed_param.py $fn_in $min_cluster_size $ndim [workers_count=$workers_count] [h=$h] [sigma=$sigma] [dq=$dq] [q2=$q2] [max_dj=$max_dj]

python variation_from_cmd_dynamic_param.py $fn_in $min_cluster_size $ndim [sigma=$sigma] [dq=$dq] [betta=$betta] [max_dj=$max_dj]
````