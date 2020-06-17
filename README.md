# DNS Anomaly Detection using a Sequence-to-Sequence Model  
## **Authors:** Matthew Grubelic, Chris Saliby, Anthony Saldana, Luke Turbert, Andrew (AJ) Rittenhouse  
## Advisors: Vahid Behzadan, Ph.D., Liberty Page 
### Sponsor: Secure and Assured Intelligent Lab (SAIL)  
**Abstract:**
The risk of crippling cyber attacks on computer systems is increasing rapidly each day. Current software and techniques used to defend against these malicious attacks are showing their limitations and are being completely overwhelmed in some cases. As a result, a more modern and forwardthinking solution is becoming increasingly necessary. The team is implementing one such software solution using a sequence to sequence neural network in Python3 with the Pytorch library to observe malicious events and predict when the next attack might happen. In this project, a deep learning sequence to sequence model, modeled after behavior of predictive typing technologies, was implemented on the DARPA 1999 dataset to detect malicious TCP traffic and determine the probability of another attack in the future. The model functions by observing sequences of network packets, using them to predict upcoming sequences of packets, and comparing the actual observed data to the prediction. Since the amount of notable research and experimentation done in this area so far is lacking, the results yielded by this network traffic anomaly detection approach further demonstrate that the use of a sequence to sequence model is a viable, though still emerging, solution for modern intrusion detection systems.  


## What is in this README.md? 

In this README.md, a quick instructional guide will be given to help in the setup and execution of the code associated with this projcet.

The project has **three main pieces of code:** The "DARPADatatsetParser.ipynb", the "Seq2SeqTraining.ipynb" and the "Seq2SeqTesting.ipynb"

The following sections of this file will explain the order of files that need to be executed and how to execute them. 

## DARPA 1999 Dataset link
**Link to main page of dataset:** https://www.ll.mit.edu/r-d/datasets/1999-darpa-intrusion-detection-evaluation-dataset 
**First week of data (attack free): ** https://archive.ll.mit.edu/ideval/data/1999/training/week1/index.html
**Second week of data (labeled attacks): ** https://archive.ll.mit.edu/ideval/data/1999/training/week2/index.html
**Third week of data (attack free): ** https://archive.ll.mit.edu/ideval/data/1999/training/week3/index.html

## DARPADatasetParser.ipynb 
* **Step 1:** Open up the DARPADatasetParser.ipynb notebook in Google Colab.
* **Step 2:** Download the "week1mon.csv" file and import it into the notebook. This is done by going to the Files | Upload | "../week1mon.csv" menu located to the left of Google Colab. (This is how you will import the other files in the project). 
* **Step 3:** Run all of the cells within the notebook. 
* **Step 4:** In the final code cell of the notebook, a file titled "testing_sequences.csv" will be created and uploaded into the Files folder of Google Colab. Download this file onto your local machine, it will be used as the input for the next notebook. 


## Seq2SeqTraining
* **Step 1:** Open up the Seq2SeqTraining.ipynb notebook in Google Colab.
* **Step 2:** Import the csv you get from the parser. (week1mon_seqs.csv)
* **Step 3:** Run all of the cells within the notebook.
* **Step 4:** In the "Training Overhead" cell there will be snapshots of the model being saved at 20%, 40%, 55%, 70%, 85%, and 100%. Each percentage represents the number of iterations the model is currently at.
* **Step 5:** Finish running the final cell of the notebook. This is where the model will run the "main" function of the code and generate the trained model parameters. 


## Seq2SeqTesting
* **Step 1:** Open up the Seq2SeqTesting.ipynb notebook in Google Colab.
* **Step 2:** Import the csv named "testing_sequences.csv".
* **Step 3:** In the "Load the models" cell, change the "encoder1.load_state_dict" and the "decoder1.load_state_dict" to any of the saved snapshot models from the Seq2SeqTraining notebook.
* **Step 4:** Run all the cells. The final cell will determine how many anomalies are in the "testing_sequences.csv"
