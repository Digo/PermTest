PermTest
========


General information
------------------

Permutation algorithms for unadjusted pair-wise significance testing and testing with adjustment for multiple comparisons. This is designed primarily for a standard IR evaluation, where one or more method is represented by vectors of real-value performance scores. Each vector element is a query-specific value of an effectiveness metric such as ERR, NDCG, or MAP. Additionally, we can compute p-values of the f-score and the accuracy for binary classification. In this case, all the values are 0s and 1s. The first row in the file represents ground truth labels.


The code is released under the Apache License Version 2.0 http://www.apache.org/licenses/.


 For technical/theoretical details see:
 
   Leonid Boytsov, Anna Belova, Peter Westfall, 2013, 
   [Deciding on an Adjustment for Multiplicity in IR Experiments.](http://boytsov.info/pubs/sigir2013.pdf)
   In Proceedings of SIGIR 2013. [**[BibTex]**](http://dblp.uni-trier.de/rec/bibtex/conf/sigir/BoytsovBW13)
   
 If you use our software, please, consider citing this paper.


Software description
------------------

**EvalUtil**:  

 * The test program itself: _permtest_. It accepts a matrix of performance scores (ERR, MAP, etc).  
 * Each row of the matrix represent one retrieval method (called run in TREC terminology).  
 * Column I represents performance scores for the I-th query.  
 * In the case of binary classification, all values are 0s and 1s. **The first** row represents ground truth labels.  
 * An R-script _SignTest.R_ which carries out a sign test for the purpose of binary classification. The input format is the same as for the utility _permtest_ (in the case of **binary classification**). However, _SignTest.R_ can compare only **two** outputs/systems at a time, but it can handle multiple classes. To this end, it relies on the SignTest.

**ConvScripts**:
 
 * Scripts to convert TREC output file (to the matrix format).  
 * Each script accepts a registry file, which lists names of the files, which contain an output of a TREC evalution utility, e.g., trec_eval.   
 * Each such file should represent a single run.  

**A working example:**

    
 1) Compile the Eval util  
 2) Go to the directory SampleData  
 3) Run the shell script sample_run.sh  
 4) Read the comments inside the script  



