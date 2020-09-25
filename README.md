# Chronicle-rule
Codes for the paper ["Combining Chronicle Mining and Semantics for Predictive Maintenance in Manufacturing Processes"](http://www.semantic-web-journal.net/content/combining-chronicle-mining-and-semantics-predictive-maintenance-manufacturing-processes-1), published at the [Semantic Web Journal](http://www.semantic-web-journal.net/).

The running of the software starts with the frequent chronicle mining process, after which a set of frequent chronicles are extracted from raw industrial data. Frequent chronicle mining has is applied to industrial data sets for extracting temporal information of events and to predict potential machinery failures. More details on frequent chronicle mining can be referred in the paper [On mining frequent chronicles for machine failure prediction](https://link.springer.com/article/10.1007/s10845-019-01492-x).

To use domain ontologies and rules for failure prediction, a novel algorithm is developed and implemented in the codes to generate predictive [Semantic Web Rule Language(SWRL)](https://www.w3.org/Submission/SWRL/) rules. The generated rules are constructed for predicting the occurrence time of machinery failures in the future. The proposed rules provide explicit knowledge representation and semantic enrichment of failure prediction results, thus easing the understanding of the inferred knowledge. 

## Running the tests
Some input data sets are in the "data" folder under the project root dictionary. They can be passed to the command line arguments for running the software. For example, to run on the db500_ss10_dic_5_items3.data data set with support value of 0.7851234: -p -if D:\XX\XX\XX\data\input\db500_ss10_dic_5_items3.data -of D:\XX\XX\XX\data\output\result.txt -m 0.7851234.

## Some examples
The figure below demonstrates how the rule that describes different events and temporal constraints can be constructed from a chronicle. Within the rule, Chronicle stands for the root class of all the chronicle individuals in the ontology. hasEvent is the object property that links individuals of the class Chronicle and those under the class Event. hasA1V, hasA2V, hasA3V, and hasA4V are data properties that assign quantitative values of attributes to the two individuals A and B under the Event class. TimeInterval corresponds to the root class of all individuals of time intervals. 

![Alt text](https://github.com/caoppg/Chronicle-rule/blob/master/Screemshots/Chroniclefailure.png?raw=true "Chronicle to a rule")

The temporal constraints comprise the minimum time duration between an event with the failure, described by the data property hasMinF, and the maximum time duration between an event with the failure, described by another data property hasMaxF. The result of another rule generation is shown in the figure below. In this rule, hasA58V, hasA63V, hasA64V, hasA102V, hasA204V, hasA209V, hasA347V, hasA476V are data properties in the MPMO ontology that link individuals of the Event class with XML Schema Datatype values.

![Alt text](https://github.com/caoppg/Chronicle-rule/blob/master/Screemshots/ScreenshotCF5.JPG?raw=true "Chronicle to a rule in software")




