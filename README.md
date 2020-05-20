# DEBV_calculator
#### Developers: Siavash Salek Ardestani & Younes Miar (May-2020)
## 1. A short description
* The DEBV_calculator is a module for deregressing estimated breeding values (DEBV) based on blupf90 outputs and our defined dataset format (DEBV_calculator input format) using two former popular methods (Garrick et al. 2009; VanRaden et al. 2009) in Linux. The source codes of this module were written in python (by employing pandas, numpy, argparse, time, and sys libraries), and bundled by using pyinstaller (https://www.pyinstaller.org/).


## 2. Inputs and runing
### Type 1 (DEBV_calculator):
The input format DEBV_calculator module must be named exactly like this:

| ID| dam.ID  | sire.ID|EBV.Progeny|sire.EBV| dam.EBV| PA      |sire.ebv.rel|dam.ebv.rel| progeny.ebv.rel|PA.rel          |
| :-|:------- | ------ |:---------:| ------:| :------|:------- | ---------- |:---------:| --------------:|------          |
| 5 | 3       | 1      |-2.25      |-3.81   |-1.83   |-2.82    |0.86        |0.58       |0.73            |0.73            |
| 6 | 3       | 1      |-3.14      |-3.81   |-1.83   |-2.82    |0.86        |0.58       |0.48            |0.73            |
| 7 | 4       | 5      |1.79       |-0.79   |-2.00   |-1.39    |0.69        |0.50       |0.45            |0.73            |
