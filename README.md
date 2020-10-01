# RHE-mc
Randomized Heritability Estimation for Multi-variance Components



## Prerequisites
The following packages are required on a linux machine to compile and use the software package.
```
g++
cmake
make
```

## How to install :

```
git clone https://github.com/alipazokit/RHE-mc.git
cd RHE-mc
mkdir build
cd build/
cmake ..
make
```

# Documentation for RHE-mc
An executable file named RHEmc will be in build folder after the installation steps. Run RHE-mc as follows:
 ```
 ./RHEmc <command_line arguments>
```
## Parameters

```
genotype (-g) : The path of  genotype file
phenotype (-p): The path of phenotype file
covariate (-c): The path of covariate file
annotation (-annot): The path of annotation file.
num_vec (-k) : The number of random vectors (10 is recommended)
num_block (-jn): The number of jackknife blocks. (100 is recommended)
out_put (-o): The path of output file.
memory efficent mode (-mem): The flag states whether to use a memory effecient version of code. The memory efficient version is a little slower  than the not efficient version (default: false)

```
## File formats
```
Genotype : It must be in bed format.
Phenotype: It must have a header in the following format: FID IID name_of_phenotype
Covariate: It must have a header in the following format: FID IID name_of_cov_1 name_of_cov_2  . . .   name_of_cov_n
Annotation: It has M rows (M=number  of SNPs) and K columns (K=number of annotations). If SNP i belongs to annotation j, then there is  "1" in row i and column j. Otherwise there is "0". (delimiter is " ")

1) Order of individuals must be same in phenotype, gentype and covariate files.
2) Order of SNPs must be same in bim file and annotation file.
3) Annotation file does not have a header.
```
## Toy example 
To make sure that everything works well, sample files are provided in example directory. Look at test.sh file and run it  :
```
chmod +x test.sh
./test.sh
```






