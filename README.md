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
          - Linear regression
          - SVM with different kernels
          - NN
    - Is extracting the molecule descriptors of the molecules more effective than using fingerprints?
  - Which machine learning models work best for this task?
  - Does the similarity of a target molecule to the training set affect its abiliy to be accurately predicted?

#### Notebooks
- main.ipynb: General exploration to see if we can predict lipophillicity values of molecules given a molecular fingerprint

#### Conda/environment setup

`conda create -c rdkit -n rdkit-env rdkit python=3.6`

`conda activate rdkit-env`

`conda install jupyter-notebook pandas scikit-learn keras tensorflow xlrd`

`jupyter-notebook`
