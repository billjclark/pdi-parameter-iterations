# pdi-parameter-iterations

##Overview

A Pentaho example transformation that iterates through a list of parameters and calls another transformation with each set of parameter iteration.

##Use cases
This technique is ideal for having to extract data from or input to identical data sources. For example, many companies maintain identical databases
for every customer that varies only by their connection information. Instead of having a transformation for each database, swap out connection 
information with parameters and run the same transformation again.

##Technique
The overall idea is that a parent transformation that iterates through a list of parameters and calls child transformations
with each set of parameters. The child transformations will execute identically except for the changes caused by the parameter values. The
parent transformation can call as many children transformations as needed.  The logging
in the parent transformation 

##Example
The parent transformation in this example iterates through a list of connections and executes a child transformation that 
##Components

* ParameterList.csv - Comma seperated file of the parameters that you want to cycle through.
* Child1.ktr - Sample child template that gets executed with every row of parameters.
* Parent.ktr - Master transformation that calls the template with each rows of parameters from the CSV file.
* Parameterized Connection - Create a special connection where the connection properties is ${DB_HOSTNAME}

