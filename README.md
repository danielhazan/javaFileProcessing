# javaFileProcessing

In this project I implement a flexible framework for working with files. Your program will filter
the files in a given directory according to various conditions, and order the filenames that passed 
the filtering according to various properties

===============================
RUNNIG INSTRUCTIONS -->
===============================
invoked from the command line as follows:
java 'filesprocessing.DirectoryProcessor' 'sourcedir' 'commandfile'
Where:
11. sourcedir is a directory name, in the form of a path (e.g., “./myhomeworks/homework1/”
or “./myhomeworks/homework1”). This directory is referred to in the following as
Source Directory. sourcedir can be either absolute or relative to where we run the
program from.
2. commandfile is a name of a file, also in the form of a relative or absolute path (e.g.,
./scripts/Commands1.txt). This file is referred to in the following as Commands
File. It is a text file that contains sections, wherein each section contains a FILTER
and an ORDER subsections (see section 4). The FILTER sub-section includes filters
which are used to select a subset of the files in the Source Directory .The ORDER
sub-section indicates in which order the files’ names should be printed.

========================
FILES  -->
========================
1)DirectoryProcessor.java - contains the main method running the program
2)commandFileHandler.java - contains methods that read the commandFile line by line and split it into sections and subsectioN
3)Section.java - this class contains the Factory which creates the subsections of each Section i.e Filter and Order
4)Filter.java - this class contains methods which filter the given Files Array according to the case given in the SubSection
4)Order.java - this class contains methods which order the given Files Array according to the case given in the SubSection l
5)SubSectionNamesException.java -this class extends Exception, contains the methods which deal with the type2 exceptions 

=============================
= Design =
=============================
most of the design patterns are the same as presented in the UML , except of the Factory method which was added to the Secti
and was aimed to better organize the data taken from the commandFileHandler. the program was eventually modular and was easy
because the flow of the code was correct and the with logic heirarchy.
also some changes were made with the handling of the Errors type2. as we mentioned in the UML, errors of type1 were handled
Filter and Order Classes without throwing it to the main class. thus, the errors type1 were handled properly in the heirachy
ErrorsType2 had to be handled in the Section and CommandFileHandler classes throwing the exceptions to the main class, becau
are derived from incorrect Format of the CommandFile. thus, the design heirarchy of our program was matched to handling thes
pretty well.
=============================
= Implementation details =
=============================

Mostly we’ve used the comparable/comparator concept. we made a new brand comparator that sorted the list strings into types
thier default compareTo Methods. because String is a comparable class we had to change he compareTo method it uses in a way
a new comparator and invoked it by calling compareTo with two objects again.
