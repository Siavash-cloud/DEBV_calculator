# DEBV_calculator



###### Developers: Siavash Salek Ardestani & Younes Miar (May-2020)
## 1. A short description
* The DEBV_calculator is a module for deregressing estimated breeding values (DEBV) based on two former popular methods (Garrick et al. 2009; VanRaden et al. 2009) in Linux. The source codes of this module were written in python (by employing pandas, numpy, argparse, time, and sys libraries), and bundled using pyinstaller (https://www.pyinstaller.org/).


## 2. Inputs and usage
### 2.1. Type 1 (our defined format using DEBV_calculator)
#### 2.1.1. Input
The input header must be named exactly like this:

| ID| dam.ID  | sire.ID|EBV.Progeny|sire.EBV| dam.EBV| PA      |sire.ebv.rel|dam.ebv.rel| progeny.ebv.rel|PA.rel          |
| :-|:------- | ------ |:---------:| ------:| :------|:------- | ---------- |:---------:| --------------:|------          |
| 5 | 3       | 1      |-2.25      |-3.81   |-1.83   |-2.82    |0.86        |0.58       |0.73            |0.73            |
| 6 | 3       | 1      |-3.14      |-3.81   |-1.83   |-2.82    |0.86        |0.58       |0.48            |0.73            |
| 7 | 4       | 5      |1.79       |-0.79   |-2.00   |-1.39    |0.69        |0.50       |0.45            |0.73            |
#### 2.1.2 Usage
"./DEBV_calculator --i /Data.txt --h2 0.25 --c 0.5 --o DEBV.txt"

Argument      |Description
------------- |----------------
```--i```     |     input path
```--h2```     |    heritability (0<h2<1) 
```--c```     |   fraction of genetic variance not explained by markers
```--o```     |     output path
### 2.2. Type 2 (using  blupf90 outputs and DEBV_calculator_blupf90)
#### 2.2.1. Input and usage
In the first step, you must Remove blupf90 solutions file header using: "sed '1d' solutions > solutions2"
##### Note: The standard errors must have been included in your blupf90 solutions through "OPTION sol se" command in blupf90.
##### Then, run this command:
"./DEBV_calculator_blupf90 --s solutions --op Ped.txt --rp renadd03.ped --rt 1 --re 3 --h2 0.25 --va 18 --c 0.5 --o DEBV.txt"
Argument      |Description
------------- |----------------
```--s```     |     solutions path
```--op```     |    original pedigree path 
```--rp```     |    recoded (blup90) pedigree path
```--rt```     |    renumbred trait (in blup90 solutions file)
```--re```     |    renumbred effect (in blup90 solutions file)
```--h2```     |    heritability (0<h2<1) 
```--va```     |   additive variance
```--c```     |   fraction of genetic variance not explained by markers
```--o```     |     output path
## References


###### Garrick, D.J., Taylor, J.F., and Fernando, R.L. 2009. Deregressing estimated breeding values and weighting information for genomic regression analyses. Genetics Selection Evolution 41(1): 55.
###### VanRaden, P., Van Tassell, C., Wiggans, G., Sonstegard, T., Schnabel, R., Taylor, J., and Schenkel, F. 2009. Invited review: Reliability of genomic predictions for North American Holstein bulls. Journal of dairy science 92(1): 16-24.


