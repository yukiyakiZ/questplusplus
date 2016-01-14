# QuEst++
Pipelined quality estimation.

## System requirements
QuEst++ has two independent modules: *Feature Extractor Module* (developed in Java) and *Machine Learning Module* (developed in Python). The Java and python required are:

1. [Java 8](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)(JDK-1.8)
2. [Python 2.7.6](https://www.python.org/downloads/) (or above - only 2.7 stable distributions)
  1. [SciPy and NumPy](http://www.scipy.org/install.html) (SciPy >=0.9 and NumPy >=1.6.1)
  2. [scikit-learn](http://scikit-learn.org/stable/install.html)

For baseline feature extraction for sentence and document-level the following tools are also required:

1. [Perl  5](https://www.perl.org/get.html) (or above)
2. [SRILM](http://www.speech.sri.com/projects/srilm/manpages/) (for Language Model features only)

**Please note:** 

1. For Linux, **QuEst++** *Feature Extractor Module* works with both Oracle and OpenJDK distributions.

## Build
You can build using [NetBeans](https://netbeans.org/downloads/) (version 8.1) - recommended.

Alternatively, you can use [Apache Ant](http://ant.apache.org/bindownload.cgi) (>= 1.9.3):

  `ant "-Dplatforms.JDK_1.8.home=/usr/lib/jvm/java-8-<<version>>"`
  
The ant command will create all classes needed to use QuEst++ and a QuEst++.jar file.


## Basic Usage
1.Document-level:

  `java -Xmx10g -XX:+UseConcMarkSweepGC -classpath build/classes:lib/commons-cli-1.2.jar:lib/stanford-postagger.jar:lib/BerkeleyParser-1.7.jar shef.mt.DocLevelFeatureExtractor -tok -case true -lang english spanish -input input/source.doc-level.en input/target.doc-level.es -config config/config.doc-level.properties`
  
Omit the option `-tok` if the input files are already tokenised.
The option `-case` can be `no` (no casing), `true` (truecase) or `lower` (lowercase)
