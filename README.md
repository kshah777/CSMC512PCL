# CSMC 516- Detection of Patronizing and Condescending Language


The detection of Patronizing and Condescending language:

In this github repository, there is 4 different files.

* dontpatronizeme_pcl.tsv - This is the raw dataset that is used in the analysis and originaly created by Perez-Almendros. 

* Python_Script_PCL_Detection.ipynb - This it the python script used for the task of PCL detection. Note, this also has a link to google collaboratory.

* Readme - This is what you are currently reading. Gives details on how to run program and what is contained in this repository. 

* Install.md - This gives instalation instructions in order to run the program. Hint: If your computer/browser can run google collaboratory, no other instilation is needed. 

With how the permissions are set up, one should be able to click on Python_Script_PCL_Detection1.ipynb, click on the open in collab badge to open collab in a new window, and the program should be able to run. If there are issues clicking on the collab bade, right click and select open in new tab. The collab file can also be found at this [Link](https://colab.research.google.com/github/kshah777/CSMC512PCL/blob/main/Python_Script_PCL_Detection6.ipynb)
When it comes to importing the data, just log in with any google account and it should allow the program to preceed. If there are issues there, download the data file from this repository, upload to your google drive, and adjust the file-id in the program resepctively. 
A user should be able to modify the hyper parameters in the hyperparameter code block, but these changes can not be saved. The hyperparameters saved are the default/suggested parameters. The hyper parameters and what they do will be detailed below. 

In the neural network block, you will find 3 different networks of varying complexity. We did not see any increase in the accuracy of the results from increasing the size/complexity of the neural network. Larger networks seemed to be overtrained more easily and have more variable results potentially due to the more local minima. 

If you have any issues, please reach out to barrowqa@vcu.edu

PS: You likely know this, but within the toolbar of google collab there is an option called runtime. If you click here, one can hit run all to run all blocks of code sequentially.

# Hyper-Parameters

**Data-PrePre-processing parameters**
* remove_non_strings - This parameters tells the program to remove non/empty strings. The default dataset has 1 entry that is empty, this is required to be true or errors will occur (Default = True)

**Data-Pre-processing parameters**
* expand_contractions - Tells program to expand all contractions (Default = True)
* remove_punctuation - Tells program to remove all punctuation (Default = True)
* make_lowercase - Makes sentences lower case. Bert model used is uncased and I think TFIDF is uncased, so this input is not very impactful (Default = True)
* remove_stop_words - Removes common stop words, list of words removed will be printed (Default = True)
* lemmatization - Perform lemmatization/word form reduction. A variant of stemming that results in actual words (Default = True)

**Post Pre-processing data splitting parameters**
* remove_too_long - This will remove sentences that are longer than the BERT max sentence length parameter. In our investigation of teh data set, it appears that the strings that are this long were read in incorrectly and are actually multiple entries globbed together. If False, BERT will truncate values that are too long(Defualt = True)
* random_seed - Set a random seed to get consistent results. Note: if random seed=0, a new seed will be generated every time (Default = 0)
* proportion_train_data - Set proportion of data for training/validation (Default = 0.8)

**Full Model Paramters**
* TF_IDF - Tells program whether or not to make TF-IDF Vector Representations (Default = True)
* BERT - Tells program whether or not to make BERT Vector Representations (Default = True)

**TF-IDF Parameters**
* tfidf_maxfeatures - Tells program what number of top features should be selected in the TF-IDF for pcl and non pcl containing instances. The length of the final tf-idf vector will be double this number because 2 tf-idf matrixes are made. (Default = 384, 384\*2=768 which is the length of the BERT embedding)

**BERT Parameters**
* pre_process_BERT - Tells program whether to use the pre-processed text to create BERT embeddings or to use the raw input with no pre-processing. (Default = False)
* batch_size_param - Sets batch size for creation of BERT embeddings (Default = 16)
* max_len - Sets maximum sentence length to be passed to BERT. (Default = 256) 
* truncate - Tells BERT to truncate sentences that are too long. Must be set true or else BERT wont work if given too long of an input. (Default = True)

**Neural Network parameters**
* num_epochs - Set number of training epochs for neural network (Default = 15)
* learning_rate - Set learning rate for neural network (Default = 15)
* batch_size_nn - Set batch size for training of neural network (Default = 15)
