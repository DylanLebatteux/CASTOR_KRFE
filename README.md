# CASTOR-KRFE
* CASTOR-KRFE v1.1 Help file																		  
* Feature extractor for viral genomic classification                               
* Copyright (C) 2020  Dylan Lebatteux, Amine M. Remita, Abdoulaye Banire Diallo    
* Author : Dylan Lebatteux, Amine M. Remita													  
* Contact : lebatteux.dylan@courrier.uqam.ca

### Description
 CASTOR-KRFE is alignment-free method extracting discriminant features of optimal length from genomic sequences. It builds a prediction model with an evaluation of this one. The model can then be used to perform prediction of new sequences.

### Required softwares
* [python](https://www.python.org/downloads/) 
* [scikit-learn](https://scikit-learn.org/stable/install.html) 
* [numpy](https://numpy.org/install/)
* [scipy](https://www.scipy.org/install.html)                        
* [biopython](https://biopython.org/wiki/Download)    
* [matplotlib](https://matplotlib.org/users/installing.html) 

### Parameters
List of parameters requiring adjustment in the Main.py file :
* T : Threshold (T = 0.999 is recommended)
* k_min : Minimum length of k-mer(s)
* k_max : Maximum length of k-mer(s)
* features_min : Minimum number of features to identify
* features_max : Maximum number of features to identify
* training_fasta : Training fasta file path
* training_csv : Training cv file path
* testing_fasta : Testing fasta file path
* testing_csv : Testing cv file path

### Utilization
Specify the parameters of the previous section in the Main.py file.
Then run the following command :
```sh
$ python -W ignore Main.py 
```
Complementary information : 
- The training_fasta and training_csv are required for feature extraction, model construction and evaluation. 
- If testing_fasta and testing_csv are not specified there will be no prediction.
- If testing_fasta is specified alone, there will be a prediction without evaluation.
- Finally, if testing_fasta and testing_csv are both specified, there will be prediction with evaluation.

### Input
* FASTA : Contains the sequences in fasta format. Example : 
```sh
>id_sequence_1.description_sequence_1 
CTCAACTCAGTTCCACCAGGCTCTGTTGGATCCGAGGGTAAGGGCTCTGTATTTTCCTGC 
>id_sequence_2.description_sequence_2						
CTCAACTCAGTTCCACCAGGCTCTGTTGGATCCGAGGGTAAGGGCTCTGTATTTTCCTGC
...
...
...
>id_sequence_n-1.description_sequence_n-1												 
CTCAACTCAGTTCCACCAGGCTCTGTTGGATCCGAGGGTAAGGGCTCTGTATTTTCCTGC 
>id_sequence_n.description_sequence_n															 
CTCAACTCAGTTCCACCAGGCTCTGTTGGATCCGAGGGTAAGGGCTCTGTATTTTCCTGC 
```




* CSV :  Contains the classes associated with each sequence. Example :

id_sequence_1,class_sequence_1																 
id_sequence_2,class_sequence_2																		 
...																		 
...																			 
...	
id_sequence_n-1,class_sequence_n-1																 
id_sequence_n,class_sequence_n	

* For more detailed examples see the data sets in the Data folder   

### Output
* Analysis.png : Show the decision graph of the optimal set of k-mers by CASTOR algorithm     
* model.pkl : Prediction model generated by CASTOR-KRFE                                        
* Kmers.txt : File of the extracted k-mers list   
* Matrice.csv: Contains the matrix formed with the extracted features
* Model_Evaluation.txt : Results file of the evaluation a model with a dataset of labeled sequences 
* Prediction_Evaluation.txt : Results file of the evaluation of the testing set 
* Prediction.csv : Results file of the prediction of unknown genomic sequences without evaluation        
* Prediction_Evaluation.csv : Results file of the prediction of unknown genomic sequences with evaluation 

### Reference to cite CASTOR-KRFE
* [Lebatteux, D., Remita, A. M., & Diallo, A. B. (2019). Toward an alignment-free method for feature extraction and accurate classification of viral sequences. Journal of Computational Biology, 26(6), 519-535.](https://www.liebertpub.com/doi/pdfplus/10.1089/cmb.2018.0239)
                                                                                   
