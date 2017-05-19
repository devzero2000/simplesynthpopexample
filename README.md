1.  simplesynthpopexample
    Examples of public datasets processed by the R synthpop package

The commands used to generate the synthesized data are (Note:
WIP) :

machbuild@ubuntu2pinto:~/proj/simplesynthpopexample/adultCOCOA$ R -q
&gt; library(‘synthpop’)
Loading required package: lattice
Loading required package: MASS
Loading required package: nnet
Loading required package: ggplot2
Find out what’s changed in ggplot2 at
http://github.com/tidyverse/ggplot2/releases.
&gt; ods = read.obs(“adult\_occ\_uniform\_5000.csv”)
&gt; head(ods)
age sex race marital education
1 29 Male White Never-married Some-college
2 43 Male Asian-Pac-Islander Never-married Some-college
3 45 Male White Never-married Some-college
4 31 Male Black Married-civ-spouse Some-college
5 39 Female White Married-civ-spouse Some-college
6 59 Male White Never-married HS-grad
country typeEmployer occupation income
1 United-States Private Guard\#1 50000+.
2 United-States Private Housekeeper\#1 –50000
3 Mexico Private Executive\#1 –50000
4 United-States Private Cleaner\#3 –50000
5 Mexico Private Carrier\#5 –50000
6 United-States Private Carrier\#5 –50000
&gt; summary(ods)
age sex race
Min. :17.00 Female:1591 Amer-Indian-Eskimo: 59
1st Qu.:28.00 Male :3409 Asian-Pac-Islander: 148
Median :37.00 Black : 484
Mean :38.39 Other : 36
3rd Qu.:47.00 White :4273
Max. :90.00

marital education country
Divorced : 697 HS-grad :1613 United-States:4553
Married-AF-spouse : 2 Some-college:1095 Mexico : 90
Married-civ-spouse :2345 Bachelors : 881 Philippines : 31
Married-spouse-absent: 61 Masters : 254 Germany : 29
Never-married :1585 Assoc-voc : 218 Puerto-Rico : 26
Separated : 182 11th : 183 Canada : 25
Widowed : 128 (Other) : 756 (Other) : 246
typeEmployer occupation income
Federal-gov : 148 Carrier\#5 :1024 –50000 :3716
Local-gov : 319 Cleaner\#3 : 875 50000+.:1284
Private :3660 Clerk\#1 : 776
Self-emp-inc : 176 Craftsman\#3: 635
Self-emp-not-inc: 462 Executive\#1: 580
State-gov : 232 Guard\#1 : 432
Without-pay : 3 (Other) : 678
&gt; my.seed &lt;- 17914709
&gt; sds.default &lt;- syn(ods, seed = my.seed)
syn variables
1 age sex race marital education country typeEmployer
