# Peter Rose Covid
goal: take the notebooks and run them on the HPC systems
learn knowledge graphs
learn neo4j

why neo4j?

KG Imports

kg import automates the ingestion 

should we get some linux vms


## Knowledge graphs
a knowledge graph is made of nodes, and in between the nodes are arrows with verbs

how do you make one of these knowledge graphs?

create CSV files with formatted data inside. The information of these csv files will be used to form the knowledge graphs
the files contain nouns, which will become the nodes

then you have another csv file with 2 nouns that LINK together. for instance

header: from        to
        STATE       CITY

this ensures the program can connect one node to another

metadata: data about data
basically is gives us a description of different aspects of a node or connector file

they all at least need a property and name

## Setup 
edit the neo4js.sh file and its username/password
./import_Neo4j.sh
import metadata and makes the knowledge graph

what does the metadata do precisely?

## Jupyter notebook queries on neo4j

py2neo import graph
find in examplequeries.ipynb

uses cypher to run queries

then you can convert queries to pandas dataframe

data is connected to metadata via file naming convention. File prefixes allow for multiple file names with the same metadata but different contents. Maybe ill use that for a file sorter

VERY SIMILAR TO THE SQL SYNTAX
# Covid knowledge graphs
heterogenous data
what is it?
data of multiple different types that we can link together meaningfully, especially for knowledge graphs

links to create:
biological
epidemioloogical
polulations characteristics

all into location. Generate relationships between everything and location

neomap, geographical mapping program

we do data science in jupyter notebooks

bolt: binary protocol to speed up neo4js quereing. Operates like regular URL. Bolt is hosted on sdsc 

how can I host a neo4js server?

write notebook to get list of properties on peters knowledge graph