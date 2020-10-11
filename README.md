# FLAME Algorithm Experiments

This is the repository for the paper FLAME: A Fast Large-scale Almost Matching Exactly Approach to Causal Inference. This contains the scripts for the experiment section in the paper. Detailed instructions are also in the comments of the scripts.

Please note that this repository is **not** intended for users. The Python package for users is in another respository: https://github.com/almost-matching-exactly/DAME-FLAME-Python-Package. We also offer an R package: https://github.com/almost-matching-exactly/R-FLAME.

## FLAMEbit example

```python
from FLAMEbit import *

df,_,_ = data_generation_dense_2(15000, 15000, 10, 5) # data generation
holdout,_,_ = data_generation_dense_2(15000, 15000, 10, 5) # data generation (the holdout set)

res = run_bit(df = df, holdout = holdout, covs = range(15), covs_max_list = [2]*15, tradeoff_param = 0.1) % call the function

estimate, group_size = get_estimate_vectors(df, res[1], range(15)) # get result summary
```

## Note
The columns of the data table ''df'' must be reordered such that the =covs_max_list= is non-increasing from left to right. 
