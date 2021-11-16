# CSMC 516- Detection of Patronizing and Condescending Language


The detection of Patronizing and Condescending language:

In this github repository, there is 4 different files.

* dontpatronizeme_pcl.tsv - This is the raw dataset that is used in the analysis and originaly created by Perez-Almendros. 

* Python_Script_PCL_Detection1.ipynb - This it the python script used for the task of PCL detection. Note, this also has a link to google collaboratory.

* Readme - This is what you are currently reading. Gives details on how to run program and what is contained in this repository. 

* Install.md - This gives instalation instructions in order to run the program. Hint: If your computer/browser can run google collaboratory, no other instilation is needed. 

With how the permissions are set up, one should be able to click on Python_Script_PCL_Detection1.ipynb, click on the open in collab badge to open collab in a new window, and the program should be able to run. When it comes to authroizing the data, just log in with any google account and it should work. A user should be able to modify the hyper parameters in the hyperparameter code block, but these changes can not be saved. The hyperparameters saved are the default/suggested parameters. 

In the neural network block, you will find 3 different networks of varying complexity. We did not see any increase in the accuracy of the results from increasing the size/complexity of the neural network. Larger networks seemed to be overtrained more easily and have more various results due to the many local minima. 

If you have any issues, please reach out to barrowqa@vcu.edu

PS: You likely know this, but within the toolbar of google collab there is an option called runtime. If you click here, one can hit run all to run all blocks of code sequentially.
