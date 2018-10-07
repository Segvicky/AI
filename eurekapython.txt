import pandas as pd
import numpy as np
from pprint import pprint
import collections
from collections import Counter
import math
dataset = pd.read_csv('C:\\Users\\Omotayo\\.spyder\\sed\\wdpa.csv')

dataset.head()

# A function to calculate entropy in a given dataset 
def entropy(target_col):
    elements, count = np.unique(target_col,return_counts =True)
entropy = np.sum([(-counts[i]/np.sum(counts))*np.log2(counts[i]/np.sum(counts)) for i in range(len(elements))])
    #return    

def entropy(target_col):
    elements, counts = np.unique(target_col,return_counts =True)
    entropy = np.sum([(-counts[i]/np.sum(counts))*np.log2(counts[i]/np.sum(counts)) for i in range(len(elements))])
    return entropy
    
def ent(data):
    uniqw, inverse = np.unique(data, return_inverse=True)
    p_data= np.bincount(inverse)/len(data) # calculates the probabilities
    ent=entropy(p_data)  # input probabilities to get the entropy
    return ent
  
print dataset
