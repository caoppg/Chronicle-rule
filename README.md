# Chronicle-rule
Codes for the paper ["Combining Chronicle Mining and Semantics for Predictive Maintenance in Manufacturing Processes"](http://www.semantic-web-journal.net/content/combining-chronicle-mining-and-semantics-predictive-maintenance-manufacturing-processes-1), published at the [Semantic Web Journal](http://www.semantic-web-journal.net/).

The running of the software starts with the frequent chronicle mining process, after which a set of frequent chronicles are extracted from data. Frequent chronicle mining has is applied to industrial data sets for extracting temporal information of events and to predict potential machinery failures. 

To use domain ontologies and rules for failure prediction, a novel algorithm is developed and implemented in the codes to generate predictive [Semantic Web Rule Language(SWRL)](https://www.w3.org/Submission/SWRL/) rules. The generated rules are constructed for predicting the occurrence time of machinery failures in the future. The proposed rules provide explicit knowledge representation and semantic enrichment of failure prediction results, thus easing the understanding of the inferred knowledge. 

## Running the tests
Some input data sets are in the "data" folder under the project root dictionary. They can be passed to the command line arguments for running the software. For example, to run on the db500_ss10_dic_5_items3.data data set with support value of 0.7851234: -p -if D:\XX\XX\XX\data\input\db500_ss10_dic_5_items3.data -of D:\XX\XX\XX\data\output\result.txt -m 0.7851234.

