# Notes
PPOD Analysis
what kind of knowledge graph are we using?
NEO4j

the ppod have a secure bolt server to connect to 

developing software to make knowledge graphs out of any dataset. The javascript client uses a REST protocol to process all the info

## Hearsch Demo
ppod on a reusable diagnostic interface

it can support json, csv and google sheets

the user can combine the above types too and upload one of each type and combine them

the progrtam is written in vuejs

### Operation
1. input files throuhg the web portal
2. select colors of nodes, and create relationships visually
3. create relationships between tables based on common column names. For instance you can associate two tables by organization name.

in progress features:
* search bar
* an edit function that allows users to edit uploaded data
* way to save uploading data

drawbacks
* javascript needs proper backend to handle data
* needs proper backend for google sheets

future features
* more sources of data
* save data to private database
* define hover properties that allow users to hover over nodes and see more details
* give user more relation options
* add feature to save data as knowledge graph

Tapis:
1. Need the private and public key
2. upload the file
3. need dataapp json dataset, like obtained from curl
4. run the containerized job

clone the repo
get the accounts from tacc 
try to get the tapis notebook running
