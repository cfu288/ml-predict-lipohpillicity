ML methods to predict lipophillicity
====================================
- Quick presentation about this project can be found [here](https://github.com/cfu288/ml-predict-lipohpillicity/blob/master/Presentation.pdf)

#### Summary
- In drug discovery, finding a lead compound is difficult and expensive and requires time consuming manual testing in a laboratory to find a good lead compound.
- If we can predict properties of a compound based off its structure without testing each compound, we can find lead compounds quicker and cheaper.
- Lipophillicity of a compound is usually a key factor in the ADME properties of compound. I will try to predict these values given only the SMILES structure of a molecule.

#### Dataset
- I will use the “Lipophilicity_Dataset_-_logD7_4_of_1_130_Compounds” dataset published by Wang (2015). 

#### Objectives
- To experiment with different ml toolkits like sci-kit learn and tensorflow+keras on this lipophillicity dataset.
- I hope to answer a few research questions found below:
  - Can we predict lipophillicity values of molecules given their structure?
    - Can we use molecular fingerprints as a way to encode structure for this task?
      - Which type of fingerprint performs best?
      - Which model performs best?
          - Linear regression
          - SVM with different kernels
          - NN
    - Is extracting the molecule descriptors of the molecules more effective than using fingerprints?
  - Which machine learning models work best for this task?
  - Does the similarity of a target molecule to the training set affect its abiliy to be accurately predicted?

#### Notebooks
- 1_main.ipynb: General exploration to see if we can predict lipophillicity values of molecules given a molecular fingerprint, try to perform regressions using SKlearn on molecular data
- 2_PCA.ipynb: Experimenting with PCA for speeding up training time/visualizations
- 3_NN.ipynb: Experimenting with a neural network regression model using Keras and Tensorflow

#### (Tentative) Results and Conclusions
- Lasso : 
    - r^2: 0.738
    - RMSE: 0.863
- Ridge :
    - r^2: 0.774
    - RMSE: 0.802
- SVR : 
    - r^2: 0.790
    - RMSE: 0.772
    - Notes: This model seemed to strongly overfit
- SVR + PCA:
    - r^2: 0.786
    - RMSE: 0.780
    - Notes: PCA seemed to help with the overfitting problem
- RF : 
    - r^2: 0.700
    - RMSE: 0.923
- NN:
    - r^2: -
    - RMSE: 0.968
    
#### Conda/environment setup

`conda create -c rdkit -n rdkit-env rdkit python=3.6`

`conda activate rdkit-env`

`conda install jupyter-notebook pandas scikit-learn keras tensorflow xlrd`

`jupyter-notebook`
