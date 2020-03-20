Matlab trick
=============================
# Func
1.nargin in function
measure the number of input:
```matlab
if nargin<1, error('Not enough input arguments.'); end
```

2.size of matrix
An [] for return several outputs is necessary:
```matlab
[nchan,nsampl]=size(x)
```

# Address
1. Addpath to the programme:
../ to return to the upper parent folder
```matlab
addpath ../utils;
```
2. mkdir
```matlab
if ~exist(edir,'dir'), mkdir(edir); end
```
