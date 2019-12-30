Author: Shafiq Joty [sjoty@qf.org.qa]


For parsing a raw text, you should run discourse segmenter followed by discourse parser.  

------------------------
Running Discourse Segmenter:

Command:
	python Discourse_Segmenter.py <infile>

Required packages/tools:

1. Charniak's reranking parser (Available from https://github.com/BLLIP/bllip-parser). 
	a. put it in Tools/CharniakParserRerank and install it.

2. Taggers from UIUC (from http://cogcomp.cs.illinois.edu/page/software)
	a. Download POS tagger and shallow chunker [LBJPOS.jar, LBJChunk.jar, LBJ2.jar, LBJ2Library.jar]
        b. Put these in Tools/UIUC_TOOLs/

3. Install scikit-learn and scipy (see for example: http://scikit-learn.org/stable/install.html)

4. Install java if not installed (see for example: https://help.ubuntu.com/community/Java)

5. Make sure the Tools/SPADE_UTILS/bin/edubreak is set to executable.

6. Now run the segmenter using the command above. If it shows errors in apply_model method in loading the model, then it is due to differnt versions of the logistic regression in sklearn. 
	- To overcome this, open the commented "train_model" in do_segment method and run the segmenter. This learns the model and saves it. 
        - If it runs once, you don't need to run train_model again. You should comment it to save time. 

---------------------
Running Discourse Parser:

Command:
	python Discourse_Parser.py <discourse segmented file> 

Required packages:

1. Install wordNet (for example, On ubuntu you can write: apt-get install science-linguistics) and set the WNHOME environment variable to the WordNet directory. WNHOME should contain the dictionary files. 
2. Install WordNet::QueryData (http://search.cpan.org/dist/WordNet-QueryData/QueryData.pm; also provided). To install it properly you may need to set the $wnHomeUnix and $wnPrefixUnix to the appropriate directories.

License:
The Discourse Parser is an Open Source Software, and is released under the Common Public License. You are welcome to use the code under the terms of the licence for research purposes ONLY, however please acknowledge its use with a citation:

[1] Shafiq Joty, Giuseppe Carenini, Raymond Ng and Yashar Mehdad. Combining Intra- and Multi-sentential Rhetorical Parsing for Document-level Discourse Analysis.In Proceedings of the 51st Annual Meeting of the Association for Computational Linguistics (ACL 2013), Sofia, Bulgaria

[2] Shafiq Joty, Giuseppe Carenini and Raymond Ng. A Novel Discriminative Framework for Sentence-Level Discourse Analysis. In Proceedings of the Conference on Empirical Methods in Natural Language Processing and the Conference on Natural Language Learning (EMNLP-CoNLL 2012), Jeju, Korea.


