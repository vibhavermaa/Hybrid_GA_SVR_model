# Hybrid_GA_SVR_model

Given a dataset with n number of features, I want to select thoses feature subset which will, after trained on SVR model give me better estimates. 

To apply genetic algorithm in this problem, we first have to create population, which is a set of chromosomes. Each chromosomes is structured as 

### chromosome = [f1,f2,...,fn, C,gamma,epsilon] 

where f1,f2...fn represents each feature of the dataset and rest are SVR hyper parameters gamma, epsilon and C.

Here, for all i, fi=(-0.5,0.5) where i = 1 to n and gamma = (0.1 , 1), epsilon = (0.1 , 1), and C = (1,1000).
Each chromosomes is the set of (n+3) values that we have generated randomly from the given range of values.


### fi = (-0.5,0.5), if  fi < 0 , the feature fi is rejected
###                  if fi > 0 , feature fi is selected for training the SVR model.
                 
   
   
GA applies selection, crossover and mutation to give the optimized result. We are applying GA to get the chromosome that will give me minimized fitness value. 


In terms of the problem statement, Each chromosome in the population actually tells the required features and SVR hyperparameters chosen for training and testing the SVR model (refer evaluation function in the code.). So, We are evaluating each chromosomes's fitness value (i.e the MSE after testing the SVR model) and select those chromosomes havibng lower fitness value (minimum error). 


#### In the code, init_svr is the population which we have initialized to pop inside BGA class.
                 
                 
