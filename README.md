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

