# DiscreteEstimator

This Julia script will look in a .mat file for data, and calculate the mutual information for one discrete and one continuous variable. It relies, as the underlying method does, on the continuous variable being in the form of a n x n dimensional distance matrix.

This should be run passing the location of the MATLAB file as an argument
    `julia discreteEstimator.jl "mydata.mat"`

To calculate MI, an n length array of labels, and n x n distance matrix are required. 
To facilitate doing this multiple times, the script expects an array of label sets and an array of distance matrices, named `labels` and `distances` in the .mat file.

For example, calculating 4 MIs using n = 1000, `labels` should, in MATLAB, be `4x1000 double` and `distances` be `4x1000x1000 double`.

The results are saved in to a CSV in the same order as in the data file. 
The MAT package in Julia sadly errors when saving back to the .mat, hence the CSV.

As for dependencies, this script requires these Julia packages : `Optim, Distributed, MAT, Distributions, DelimitedFiles`.
These can be installed by entering a julia session, pressing `]` for the package manager, then `add Optim, Distributed, MAT, Distributions, DelimitedFiles`.

```
> julia
(@v1.5) pkg>
(@v1.5) pkg> add Optim, Distributed, MAT, Distributions, DelimitedFiles
```
