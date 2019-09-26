# Categorical-Feature-Encoding

Method 1: Label encoding 
In this method we change every categorical data to a number.That is each type will be subtituted by a number. For example we will substitute 1 for Grandmaster,2 for master ,3 for expert etc.

Three steps to label encode our data:
Initialize the labelencoder class
Call the fit() method to fit the data
Transform data to labelencoded data

Method 2 : On hot encoding 
Our second method is encoding each category as a one hot encoding. 
OHE is a representation method that takes each category value and turns it into a binary vector size.

Method 3 : Feature hashing (a.k.a the hashing trick) 
Feature hashing is a very cool technique to represent categories in a “one hot encoding style” as a sparse matrix 
but with a much lower dimensions. In feature hashing we apply a hashing function to the category and then represent it by its indices. 
If we choose a dimension of 5 to represent “New York” we will calculate H(New York) mod 5 = 3 (for example) 
so New York representation will be (0,0,1,0,0).

Method 4 :Encoding categories with dataset statistics 
Now we will try to give our models a numeric representation for every category with a small number of columns but with 
an encoding that will put similar categories close to each other. The easiest way to do it is replace every category with the 
number of times that we saw it in the dataset. This way if New York and New Jersey are both big cities, 
they will probably both appear many times in our dataset and the model will know that they are similar.

Method 5 :Encoding cyclic features
A common method for encoding cyclical data is to transform the data into two dimensions using a sine and consine transformation.

Method 6 : Target encoding 
Target-based encoding is numerization of categorical variables via target. In this method, we replace the categorical variable 
with just one new numerical variable and replace each category of the categorical variable with its 
corresponding probability of the target (if categorical) or average of the target (if numerical). 
The main drawbacks of this method are its dependency to the distribution of the target, 
and its lower predictability power compare to the binary encoding method.

Method 7 :K-Fold target encoding 
k-fold target encoding can be applied to reduce the overfitting. In this method, we divide the dataset 
into the k-folds, here we consider 5 folds. Fig.3 shows the first round of the 5 fold cross-validation.
We calculate mean-target for fold 2, 3, 4 and 5 and we use the calculated values, mean_A = 0.556 and mean_B = 0.285 
to estimate mean encoding for the fold-1.
