# Chronicle-rule
Codes for the paper ["Combining Chronicle Mining and Semantics for Predictive Maintenance in Manufacturing Processes"](http://www.semantic-web-journal.net/content/combining-chronicle-mining-and-semantics-predictive-maintenance-manufacturing-processes-1), published at the [Semantic Web Journal](http://www.semantic-web-journal.net/).

The running of the software starts with the frequent chronicle mining process, after which a set of frequent chronicles are extracted from raw industrial data. Frequent chronicle mining is a more expressive version of sequential pattern mining algorithms. It is applied to industrial data sets for extracting temporal information of events and to predict potential machinery failures. A new algorithm for the extraction of frequent chronicles called *Clasp-CPM* is implemented. This algorithm generates only closed failure chronicles in an effective manner.

To use domain ontologies and rules for failure prediction, a novel algorithm is developed and implemented in the codes to generate predictive [Semantic Web Rule Language (SWRL)](https://www.w3.org/Submission/SWRL/) rules from extracted frequent chronicles. The generated rules are constructed for predicting the occurrence time of machinery failures in the future. The proposed rules provide explicit knowledge representation and semantic enrichment of failure prediction results, thus easing the understanding of the inferred knowledge. 

## Running the tests
Some input data sets are in the "data" folder under the project root dictionary. They can be passed to the command line arguments for running the software. For example, to run on the db500_ss10_dic_5_items3.data data set with support value of 0.7851234: -p -if D:\XX\XX\XX\data\input\db500_ss10_dic_5_items3.data -of D:\XX\XX\XX\data\output\result.txt -m 0.7851234.

## Some examples
The figure below demonstrates how the rule that describes different events and temporal constraints can be constructed from a chronicle. Within the rule, *Chronicle* stands for the root class of all the chronicle individuals in the ontology. *hasEvent* is the object property that links individuals of the class *Chronicle* and those under the class *Event*. *hasA1V*, *hasA2V*, *hasA3V*, and *hasA4V* are data properties that assign quantitative values of attributes to the two individuals A and B under the *Event* class. *TimeInterval* corresponds to the root class of all individuals of time intervals. 

<img src="https://github.com/caoppg/Chronicle-rule/blob/master/Screemshots/Chroniclefailure.png" width="1200">

The temporal constraints comprise the minimum time duration between an event with the failure, described by the data property hasMinF, and the maximum time duration between an event with the failure, described by another data property hasMaxF. The result of another rule generation is shown in the figure below. In this rule, hasA58V, hasA63V, hasA64V, hasA102V, hasA204V, hasA209V, hasA347V, hasA476V are data properties in the MPMO ontology that link individuals of the Event class with XML Schema Datatype values.

![Alt text](https://github.com/caoppg/Chronicle-rule/blob/master/Screemshots/ScreenshotCF5.JPG| width=48 "Chronicle to a rule in software")

## The ontology reasoning and failure prediction GUI
Failure prediction is achieved by using the [Drools rule engine](https://www.drools.org/) to perform ontology reasoning on the data that is populated in the domain ontologies. After prediction, a SQWRL query is created to retrieve the prediction results. The SQWRL language takes an antecedent of a SWRL rule and effectively treats it as a pattern specification for a query. To extract the results, a SQWRL query replaces a rule consequent with a retrieval specification.

## Built with

* [Maven](https://maven.apache.org/) - Dependency Management
* [Protégé](https://protege.stanford.edu/) - An ontology editor and framework for building intelligent systems
* [The OWL API](http://owlapi.sourceforge.net/) - An API for OWL 2 and an efficient in-memory reference implementation.
* [The SWRL API](https://github.com/protegeproject/swrlapi) - A Java API for working with the OWL-based SWRL rule and SQWRL query languages.
* [The SQWRL API](https://github.com/protegeproject/swrlapi/wiki/SQWRL) - A SWRL-based query language providing SQL-like operators for extracting information from OWL ontologies.
* [SPMF](https://www.philippe-fournier-viger.com/spmf/index.php?link=download.php) - A Java Open-Source Data Mining Library.
* [Weka](https://www.cs.waikato.ac.nz/ml/weka/) - An open source machine learning software.

## Author

* **Qiushi Cao** - *Ph.D. student at INSA Rouen Normandie* 
* Email: qiushi.cao09@gmail.com

## License
This project is licensed under the MIT License - see the [License.md](License) file for details




