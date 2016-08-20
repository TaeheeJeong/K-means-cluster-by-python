# K-means-cluster
K-means cluster analysis by python

A k-means cluster analysis was conducted to identify underlying subgroups of adolescents based on their similarity of responses on 11 variables that represent characteristics that could have an impact on school achievement. 

## The 11 variables are following.
alcevr1 (1=yes, 0=no): whether or not the adolescent had ever used alcohol    
marever1 (1=yes, 0=no): whether or not the adolescent had ever used marijuana   
alcprobs1 (scale 0-6): quantitative variables measuring alcohol problems   
deviant1 (scale) : a scale measuring engaging in deviant behaviors     
(such as vandalism, other property damage, lying, stealing, running away, driving without permission, selling drugs, and skipping school)    
viol1 (scale) : a scale measuring violence   
dep1 (scale) : a scale measuring depression   
esteem1 (scale) : a scale measuring self-esteem   
parpres (scale) : parental presence   
paractv (scale) : parental activities   
famconct (scale) : family connectedness   
schconn1 (scale) : school connectedness   

##  All clustering variables were standardized to have a mean of 0 and a standard deviation of 1.

##  Data were randomly split into a training set that included 70% of the observations (N=3202) and a test set that included 30% of the observations (N=1373). 

# OUTPUT
## Elbow plot  
A series of k-means cluster analyses were conducted on the training data specifying k=1-9 clusters, using Euclidean distance. 
The variance in the clustering variables that was accounted for by the clusters (r-square) was plotted for each of the nine cluster solutions in an elbow curve to provide guidance for choosing the number of clusters to interpret.   

figure: selecting k with the Elbow method2.png

The elbow curve was inconclusive, suggesting that the 2, 3 and 8-clusters. 

## The 3-cluster solution is described below.
Canonical discriminant analyses was used to reduce the 11 clustering variable down a few variables.
A scatterplot of the first two canonical variables by cluster are shown.

figure: Scatterplot for Canonical variables for 3 clutsters.png

The two clusters are relatively overlap each other and another cluster is generally distnct. The results of this plot suggest that the best cluster solution may be not 3 clusters. 

## The 2-cluster solution is described below.

figure: Scatterplot for Canonical variables for 2 clutsters.png

The two clusters are generally distinct. The result shows that 2 cluster solution would be best fitted.  

## For the 2-cluster, clustering variable means was calculated by cluster

Clustering variable means by cluster
               index   ALCEVR1  MAREVER1  ALCPROBS1  DEVIANT1     VIOL1  \
cluster                                                                   
0        3294.039323 -0.311849 -0.395225  -0.314965 -0.390028 -0.264485   
1        3268.383251  0.666337  0.854393   0.635583  0.811733  0.542640   

             DEP1   ESTEEM1   PARPRES   PARACTV  FAMCONCT  SCHCONN1  
cluster                                                              
0       -0.319537  0.269350  0.182298  0.158440  0.348749  0.358134  
1        0.631274 -0.520256 -0.379803 -0.320525 -0.720928 -0.766280 

cluster_0 has positive characters  for self-esteem, parental presence, parental activities, family connectedness, school connectedness, and no experience of alcohol, marijuana, alcohol problems, deviant behaviors, violence, and depression.
Meanwhile, cluster 1 has negative characters for self-esteem, parental presence, parental activities, family connectedness, school connectedness, and experience of alcohol, marijuana, alcohol problems, deviant behaviors, violence, and depression.
Thus, this distinction is reasonable. 

## ANOVA test
In order to externally validate the clusters, an Analysis of Variance (ANOVA) was conducted to check difference between the clusters on grade point average (GPA). A tukey test was used for post hoc comparisons between the clusters. 

Results indicated that there is significant difference between the clusters on GPA (F(2, 3202)=v, p~.0000). 
Also, the tukey post hoc comparisons showed significant difference between the two clusters on GPA. 
Adolescents in cluster 1 had the higher GPA as mean=2.96, sd=0.73, and cluster 2 had the lower GPA as mean=2.51, sd=0.78.


                            OLS Regression Results                            
==============================================================================
Dep. Variable:                   GPA1   R-squared:                       0.073
Model:                            OLS   Adj. R-squared:                  0.073
Method:                 Least Squares   F-statistic:                     252.4
Date:                Fri, 19 Aug 2016   Prob (F-statistic):           9.34e-55
Time:                        22:20:05   Log-Likelihood:                -3605.9
No. Observations:                3202   AIC:                             7216.
Df Residuals:                    3200   BIC:                             7228.
Df Model:                           1                                         
Covariance Type:            nonrobust                                         
===================================================================================
                      coef    std err          t      P>|t|      [95.0% Conf. Int.]
-----------------------------------------------------------------------------------
Intercept           2.9607      0.016    185.500      0.000         2.929     2.992
C(cluster)[T.1]    -0.4503      0.028    -15.886      0.000        -0.506    -0.395
==============================================================================
Omnibus:                      161.469   Durbin-Watson:                   2.013
Prob(Omnibus):                  0.000   Jarque-Bera (JB):               93.690
Skew:                          -0.272   Prob(JB):                     4.52e-21
Kurtosis:                       2.363   Cond. No.                         2.42
==============================================================================

means for GPA by cluster
             GPA1
cluster          
0        2.960677 
1        2.510345

standard deviations for GPA by cluster
             GPA1
cluster          
0        0.729718
1        0.781150

Multiple Comparison of Means - Tukey HSD,FWER=0.05
=============================================
group1 group2 meandiff  lower   upper  reject
---------------------------------------------
  0      1    -0.4503  -0.5059 -0.3947  True 



