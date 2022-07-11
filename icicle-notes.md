# Icicle institute
9:30 – 10:00 : * NSF and Panel Pre-meet
 
10:00 – 10:15 : Panel Meets ICICLE Team & Introductions
10:15 – 11:00 : ICICLE Presentation: Overview of the Institute
11:00 – 11:30 : Q & A Session
 
11:30 – 11:45 : Break
 
11:45 – 12:45 : ICICLE Presentation: Research Program
12:45 – 1:15 : Q & A Session
 
1:15 – 2:00 : Lunch Break
 
2:00 – 2:45 : ICICLE Presentation: Strategic Impact
2:45 – 3:15 : Q & A Session
 
3:15 – 3:30 : Break
 
3:30 – 4:30 : * Executive Session for Evaluation Team
4:30 – 5:00 : Evaluation Team Presents Questions for the Institute


## Icicle
AI system focusing on agricultural machine learning, by interconnectring worldwide with farmers and professionals to predict crop yields and other agricultural statistics. Operates on the idea of democratizing AI, necessary for the dissemination of this technology for the farmers.

## Questions
how do we achieve the goals of democratizing AI administratively? BAsically allow AI to be available to all kinds of people
orgtanizational round table, diversity initiatives. Gender equality initiatives. Bias training. IMportant thing is for it to look intentional. 
"not reflected in disjointed answers"

specify that geographic diversity is also important
"broaden the scope of icicle"
india 
europe

important, because icicle's primary goal is agricultural machine learning. More crop data means better algorithms?

# Goals and challenges
Conversational AI
model commons

## Knowledge graphs
KG Formalism: Multimodal KG for Camera Traps:
Use inspired goal: co design formalism with animal ecology, identified and analyzed public data sources, investigated KG tooling, using NEO4J
Applications, semantic search, visualization, multimodal reasoning

KG COnstruction:
LEarning organization knowledge for smart food sheds. Categorization of food sheds

Commodity flow ontology:
Compute the resiliency and efficiency of national food supply chain

## Federated Learning
How do you make ai trobust to heterogeneity of users
applicale to state of the art models
context aware and user aware

icice hosts public data and training algorithms. Generic and personalized ML models

improved modeling for pre analysis, data preperation

improved model creation

decoupled local training

data integration across multiple locations

## Conbversational AI
scale up question and answers to large graphs much faster that previous methods, with state of the art performance. Dynamically generate programs. Multihop and zero hop programs

handle the various ways users might engage in the system.

parse language to control commands?

adaptive AI for answering development demands

# Cyberinfrastructure
## high performance model training
much higher speed input and processing, efficient model architecture for training and evaluation

## control and coordination:
intelligent reslource management with tapis:
primary holdbacks on infrastructure are queue wait time, over 14 hours
predicting queue wait time then rpoactively submitting the next job leads to bad solutions

train it using 20 month training, model decreases chance of interruption significantly. What are interruptions if it all in a queue? Parallelism?

## AI for cyberinfrastructure
provide for efficient plug and play by optimizing cyuberinfrastructure for edge HPC and others

AI can be used to design CI stacks based on experience. Intelligent optimization

applications middleware and systems

important to me: KGs and models for CI

## application
Cost effective ML models for predicting speed of HPC applications. To what extent do test environments scale up to production models. When tested on scaled down inputs, how do we ensure it will still work when scaled up?

## MIddleware Intelligent Primitives
Learn from hardware with network and data sparsity, extract best performance. Portrable high performance on any hpc system, usable at the background of any AI system.

does not change accuracy, just makes it faster. New kernels have larger capacity

scheduling for transient cloud virtual machines:
Transient: low cost vms that are up to 10 times cheaper. How to mitigate preemtions and application disruption?

system for running batch applications on google preemtipble vms with scispot

reduce computing cost by 5x for cloud computing

# Privacy accountability and data integrity
## Relevance
broad challenges
focus on vision of transparency and trust with users
how do we do that with the infrastructure going forward?
advance broadly useful technical best practices. Research and practice to contribute to trust

how do we make farmers and industrial operators trust icicle enough to contribute, in such an expansive environment?

important for hello icicle

AI model commons and knowledge graph. Security and trust are essential for both. Understand the needs and environments of where operations take place

privacy, accountability, data integrity
full conjtrol of datasets to clients, fine grained access control during exchange, privacy enchangement,
privacy risk quanitification tools to guide data sharing

AI audit trails, expose information from within ICICLE infrasttructure. How has our result been achieved so that these things can be provided? How do we use icicle to reflect this informatin?

best practice for global resolvable persisten ids
model cards
data review boards

how do you leverage the opennes shes taliing about and security?

## Privacy
can all the methods, like encryption and best practice provide the privacy and trust a user wants to share their data? 
Tiny fractiuon of sensitive data leakage could lead to compromise

# Visual Analytics
lower technical barriers to the icicle system
work closely with conversational AI and software development

important for hello icicle

## challenge
produce a visual analytics solution that is data information and knowledge agnostic, what does that mean?
integrate with conversational AI. Scraped web pages

basically automate decision making on how to visualize data, smart visualization

## features
decouple data from interface code
user driven customization design patter
model running integrated with visual interfaces to ease access

# Smart food sheds
food systems, the natural human sysstems that encompass the ood system from working landscapes to human health challenges

challenges:
wide variety of data types across the systems as well as data holders and users

non specialists need access to the data

how do we receive and give data to the farmers?

store closure modeling, foodshed food flows visualization

modeling user needs

external partnership for porting of information from unstructured text

important to hello icicle! 

allow users to bring in graph data, whatever datta they have

let them have seamless movememnt between visualizationsz and raw data

national tabular data describing food movement

identify business partners using AI, identify areas of outflow, predicting changes and resilience on a map

major next tasks worked on is to work with the conversational AI.
Main issue now is that the models do not have much impact because they are hard to access. So we must create a web interface to enable non computer experts to operate

take an existing model to adapt it to a web based model

main use case for federated HPC and AI

# Digital agriculture
runtime management of edge to9 cloud resources
achieve effective and efficient crop yields

advanced HPC model training techniques 
train to use faster parallel GPUs

what is edge resource management?
swarm of drones working together to achieve a mission, like mapping crop fields, very cost effective

analyze defoliation

should the drones operate alone, or share data?
sharing data properly can double speed

plug and play architecture, modularity for the democratization

## Ecology
edge deployment of AI is necessary in many cases in ecological tracking. Tradeoffs of analysis and latency
animal ecology with edge AI will simplicy data collection and analysis

camera traps. The computation can be done on the cameras themselves. But much higher cost if the traps are damaged/stolen

# Hello Icicle
Another strategic project that brings together various elements for icicle to look at itself. The point of entry. 
how do we build a base as other applications come online? build a knowledge graph of icicle itself. 

top level: catalog of icicle and its components. Catalog of projects to deisplay projects. Overall, the project aims to turn unstructured data into visualized data. JSon for instance
bottom level: low level interface. Hello world. 

How do we make a system interface for icicle?

basically a complex authorization flow chart between server and client that allows clients to interact with the supercomputers

# Reference Architecture
broad collabaration across all thrusts. 
Provide descriptions of the functionality
supply standard definitions of abstractions
define technology adoption
basically organization and documentation

defined a set of template documetns for projects and thrusts to create
helped projects create documents
made connections between projects

making connections and integrating components of the program. How do we put everything together?

provide basic software frameworks and APIs 

imrpove the time to solution byh organizing AI algorithms

enable authomation of workflows across geographically distributed and heterogenous CI from edge to ml

build on top of tapis and extend it with new apis

intelligent tapis modules

extend tapis to the edge with edge servers

dynamic resource provisioning

# Shared CI Development
ensure icicle team has CI resources they need to carry out work
ensure the team has access and knowledge of resources. Scheduling webinars, distributing information on resources

# QNA
is there a threat of imbalanced development of thrusts that will result in inefficiency? Yes. Communication is essential. When one thrust stops making progress, the entire project should be adusted to compensate. That is a problem with any large institute
different people contribute in different ways. IMportant that the organization is structured so that it is adaptable so that people and resources can be allocated in an efficient and malleable manner

everyone must be connected

distrbuted efforts are good, but all organizations should have sufficient interconnection of those separate efforts when they must be connected eventually.

plug and play will be essential for making drone deployment and data analysis easier for fields. Make everything push a button

provide felxibility to run on the cloud on on HPC systems. Cloud is much more expensive though. 

Where would the end user benefit from using hpc over cloud. 

what are commons? open repositories of models to make plug and play easier, facilitate use of the models.

performance portrability? run models on diverse platforms

context is everything, its what gives the intelligent organization the ability to decide how datasets and models are used

# Icicle broader impacts
Unique implementation of collective impact, framework to bring about mutually reinforcing impact across icicle.
broadening participation in computing, diversity, equity, and inclusion, workforce development, and collaboration and knowledge transfer. Backbone coordination is called icicle broader impacts  backbone network

BIBN

You have 3 prongs of the project wide interleaving. The icicle thrust develops training for CI professionals, uses BIBN to reache underrepresented groups, and refactor training for greater accessibility

governance was established extended to members. Encompasses membership across core backbone and affiliates, and allies

agility toward new contributions, adaptable to new contributions

shared administrative functions to streamline communication, common progress measures and web pages

Goal:
build a culture of inclusivity on the infastructure. Increase diversity

# preparing AI ready workforce
BIBN network will help guide the process, logic models
knowledge transfer
stimulate professional growth across the team. 
Catalog training programs 

make sure the technology to make these resources accessible

objectives:
professional growth across the team
software and reference architecture projects

2 nsf cyber training events

education on the new resources is essential to make them useful

CIML

accessible resources for HPC and AI education

# Multidisciplinary INtegration and community building

community building, overllaping of 3 main fields, AI, CI, and Domain. All connected by use cases. Ecology, agriculture, and foodsheds. All 3 fields contribute to these use cases

deep integration
reference architecture
icicle enables institute scale efforts

teams meet biweekly
use cases help inform the six projects and drive new research
helps to integrate the workforce for multidisciplinary efforts on Icicle. Unified information is essential

multi organization synergy:
the use cases are providing the core disciplines and goals for producing AI infrastructure.
As a result, all the people at all the institutions are working towards a common goal and inside the same infrastructure. Extremely helpful in building up the computing infrastructure and continuum

The projects underpin everything

unified infrastructure allows AI to be enabled at the flick of a switch
this is essential for the process of democratization. Unified infrastructure streamlines the backend so the human element and national priorities can remain the focus, rather than software and hardware

interconnecet collected data on operations and feed it back into training. Broadening achievement and education, as well as democratizati9on

cross communication has been built in

Inheritance of multidsciplinary structure which has potential to grow or create new centers of AI leadership

basically interconnect different industries and turn them into their own centers of AI. Its like a cyberinfrastructure highway system, and new institutes are transport hubs and cities running on AI.

# Institute as a nexus point
increased understanding and connection between disciplines comes with experience and time
unified cyberinfrastructure allows easier multidisciplinary activities
it also makes it easier to add new organizations to the cyberinfrastructure system. Everything is about scalability

overall: how can we design intelligent cyberinfrastructure for computing?

the long term goal?
Establish a nation wide cyberinfrastructure system to ensure efficient and safe democratized access to AI and HPC





