Author: Lurdes Ruela

Title: Using LDA Topic Modeling to Quantify Idiomaticity: A Pilot Study 

Tools: To run this code, you must download the Lingpipe Jar and load it on to the IDE of your choice (Eclipse, Netbeans etc.)
(http://alias-i.com/lingpipe/web/install.html)
You must also have the ability to run R on your machine

OS used: The following was written o a Mac OS X 10.6.8 and uses Unix

Direction: Running the Runner.java file will call all the other files in the sequential order of the experiment. 

Note: Java does call unix to run an R file, please take that into consideration if running in windows and modify accordingly. Also, modify file locations to desired file location on running system

Below lists description of files within corresponding directory:

Directories
Code: Consists of all java files used within this experiment.
	Cosine.java - Main file, calls vectors, transforms strings to numeric values, computes cosine with other methods 
	CosineFunctions.java - Breaks down sections of cosine calculation to effectively calculate the cosine
	FileImporter.java - imports vectors needed for calculation right from the file, used in cosine calculation 
	FileOutputs.java -  Created with use of FileWriter to print arrays to separate individual files
	Filegrabber.java - Grab files and extracted input for further matrix construction; used for tf/tf-idf matrices 
	LdaMWE.java - calls on the LatentDirichletAllocation class in Lingpipe Java Package. It takes the standard input, tokenizing the data, and gathering other needed parameters and outputs resulting desired amount of local topic words
	LdaReportingHandler.java - a helper class to LdaMWE.java It reports and saves the output designated by the LdaMWE.java class in separate files.
	MatrixBuilder.java - Combines features and extracts them from original entities in the original files for matrix construction. Creates matrice with TF & TF-IDF values for MWE and Doc matrices 
	MatrixFileExtractor.java - Main class of the Matrix creator Full purpose is to create matrix for SVM calculations 
	PreTokenizer.java - tokenizes the text, removes numeric digits, punctuation, and non-ASCII Characters (uses Lingpipe Java Package)
	RscriptPrinter.java - creates center.R which runs the SVD calculations in R
	Runner.java - main file to run experiment; formatted to run all of experiments discussed 
	ModifiedEnglishStopTokenizerFactory.java -  Edited and modified from EnglishStopTokenizerFactory to ModifiedEnglishStopTokenizerFactory to modify the primary stoplist (place in alias.tokenizer file of Lingpipe Java Package 
	idf.java - Grab files and Calculate IDF values
	center.R - file that performs SVD calculations for all MWE categories (output of RscriptPrinter.java)
	
Results: File holds all results from 5 experiments ranging from subspace 2 to 6 in text files

Data: Contains all text files from all steps of project 
	I - Contains all idiomatic MWE's
	L - Contains all literal MWE's
	I_Stoplist - All idiomatic MWE's processed by Pretokenizer.java
	L_Stoplist - All literal MWE's processed by Pretokenizer.java
	Both - folder that held both idiomatic and literal MWE's for simpler access 
	BothLDATopics - extracted LDA topics of both idiomatic and literal MWE's
	Bothdocs - Matrices with tf-idf values of MWE categories.
	BothMatrix - SVD results called by Cosine.java to calculate cosine results

