# Apache NiFi :hand: fa18-523-56  fa18-523-83
 
| Daniel Hinders , Nhi Tran
| dhinders@iu.edu, nytran@iu.edu
| Indiana University
| hid: fa18-523-56 , fa18-523-83
| github: [:cloud:](https://github.com/cloudmesh-community/fa18-523-56/blob/master/paper/paper.md)
 
 
---
 
Keywords: NiFi, NSA, Data Stream, ETL
 
---
 
## Abstract
 
TBD
 
## Introduction
 
Big data can be fantastic source of truth for decision making and business process definition and actualization. However, the complexity of individual datasets, the variability of dataset structure and composition, and the sheer volume of data are challenges to truly leveraging big data in the real world. This is a multifaceted problem with many inherently overlapping challenges.
ETL or Extract, Transform, and Load encompass a number of potential tasks such as harvesting and moving data into a database from some other location and/or and cleaning, normalizing or even structuring data. In a case where a single dataset emerges from an ETL process and the data is somewhat structured and located somewhere predictably accessible, then we can start to leverage analytic or visualization tools to understand the data and use it to make decisions and learn things. Furthermore, productization and dissemination of that data is fairly straightforward.
 
But this is rarely where the real use case for bigdata solutions ends. The bigger challenge is dealing with disparate datasets and connecting points of information in a multi-sourced dataset environment. Consolidation of disparate data is therefore extremely important. Furthermore leveraging the the correctly sourced data out of consolidated datastore environment and then loaded this data into the correct product is challenging.
 
Apache NiFi is an application that seeks to address this big data problem. NiFi is tool that has emerged from a unique background as tool created by the National Secuirty Agency then curated and improved by the open source community.
NiFi is a customizable tool for building flexible data flows while preserving data provenance and security [@fa18-523-56-www-nifi-nifihomepage]. NiFi provides the ability to build or alter an ETL flow with a few clicks. NiFi builds Gets, Converts, and Pulls in a GUI and allows the user to build and customize the flow. [@fa18-523-56- www-nifi-issartetlsimple] This flexibility and usability is key to NIFIs value in a big data world where stovepipes and inflexibility are frequently challenges.
 
## ELT Challenges and NiFi
 
In the world of big data ETL, or Extract Transform and Load, is a prevalent in most big date projects or architecture. If the data being used is in the perfect format and structure, and the data is housed or collected in the ideal location for the end use of the data, then ETL may be superfluous. Otherwise Extract Transform and Load concepts will come into play. However, enabling ETL is frequently more difficult than it sounds. Data moving between systems effectively is tricky to setup and challenging to refactor on the fly when conditions change. Enter Apache NiFi.
 
 
## NiFi History
 
NiFi was first developed at the National Security Agency but was released as open source project to the public. "NiFi was submitted to The Apache Software Foundation (ASF) in November 2014 as part of the NSA Technology Transfer Program." [@fa18-523-56-www-nifi-forbes] Since then, Apache Foundation has used it’s volunteer organization to grow and mature the project. [@fa18-523-56-www-nifi-issartetlsimple]
 
## NiFi Features
 
NiFi incorporates a straightforward UI to engineer traceable data provence with configurable components. NiFi offers up the ability to custom build processors and incorporate them into a highly customizable flows. Through "…data routing, transformation, and system mediation logic" [@fa18-523-56-www-nifi-nifihomepage] NiFi seeks to automate data flows in a big data environment and give architects the ability to keep data flowing between evolving systems quickly. Amongst a host of features NiFi offers, one sticks out as particularly important because of the challenges associated with what the feature addresses: data errors, data inconsistency, and data irregularity handling. NiFi provides users the ability to incorporate in the flow processes to catch these non-happy path realities in big data. As new situations are discovered a user can quickly build if-then forks in the process to catch, store, or resolve the data issues.
 
 
 
NiFi's main features are:
 
Guaranteed delivery: use purpose-built persistent write-ahead log and content repository to ensure guaranteed delivery in an effective way
Web-based user interface: easy to use web-based GUI with drag and drop features that allows users to build, schedule, control, and monitor dataflow
Provenance: provide ability to track data flows through the systems with audit trail and traceability functionalities
Queue Prioritization: provide the ability to configure and prioritize job flow and determine the order of events
Secure: provide and support multiple security protocols and encryptions, as well as authorization management
Extensibility: provide flexibility by allowing pre-built and built-your-own extension the be integrated
Scalability: supports scale-out by clustering architecture as well as scale-up and scale-down [@fa18-523-83-nifi-apache][@fa18-523-83-apache-nifi-overview]
 
 
## Architecture

### NiFi Architecture Overview

* Web Server
* Flow Controller
* FlowFile Repository
* Content Repository
* Provenance Repository
* Java Virtual Machine

From the top down NiFi is web browser accessable by a NiFi hosted Web Server. NiFi processor operations are managed through the Flow Controller and the three repositories; FlowFile, Content, and Provenance work to process data on and off disk and in a NiFi flow. NiFi is hosted in the Java Virtual Machine environment or JVM. 

### Web Server

NiFi easy to use GUI is hosted on the Web Server within the JVM


### Flow Controller

NiFi central operations hub is the Flow Controller. Treads are managed and allocated to the processesors and the FlowFiles are passed through and maged through the Flow Controller. [@fa18-523-56-www-nifi-hortontransitpatterns]

### FlowFile Repository

Files in an active NiFi flow are tracked in a write ahead log so that as data moved through the flow NiFi can keep track of what is known about files as they pass through.[@fa18-523-56-www-nifi-homepagetechdoc]

### Content Repository

The real data for a flow file is in the NiFi content repository. NiFi uses simple blocks of data in a file system to store this FlowFile data. [@fa18-523-56-www-nifi-homepagetechdoc] Multiple file systems can be used in order to increase speed with multiple volumes being utilized. 

### Provenance Repository

In NiFi the provenance repository stores historic event data. The provenance data about flows is indexed to enable search of the records.


https://hortonworks.com/tutorial/analyze-transit-patterns-with-apache-nifi/section/1/
### Connector
### Flow Files
### Processors
### Routing Processors
### Data Transformation Processors
### Database Access Processors
### Setup System Integration Processors
 
 
## Use Case
What it is good for and what it is not
https://www.udemy.com/apache-nifi/

### File Transfer and Routing at MasterCard

One of the use cases for NiFi at MasterCard is file transfer mechanism. Batch processing is still a major part of MasterCard's ecosystem which requires multiple formatted flat files being created, transfered, and picked up by applications. MasterCard uses NiFi's file transfer features to convert files source into data stream and perform specific workflow to direct data into various target systems. Target system could be a messaging systems, Hadoop landing zone, databases. NiFi can also feeds data and trigger a map-reduce or spark jobs after transfer [https://dataworkssummit.com/san-jose-2018/session/using-nifi-to-simplify-data-flow-streaming-use-cases-mastercard/
].

MasterCard provided a demo which demonstrate the use case of them using NiFi to call a web services from a file transfer controller, the data flow then has a mechanism to determine which process groups NiFi should distribute data into based on file name/ format logic. The process groups contains workflow that can either feeds data to a diffrerent system, to Hadoop, or to Postgres database. Once each process flow are completed, the process status will be captured and reported into a Status Handler process [https://dataworkssummit.com/san-jose-2018/session/using-nifi-to-simplify-data-flow-streaming-use-cases-mastercard/]. 


### Streaming Analytics Solutions at OpenText Magellan

At OpenText Magellan, NiFi was utilized as part of their streaming analytics infrastrusture to allow continuous process and real-time analysis. OpenText Magellan's infrastructure involves source applications, NiFi, Apacha Spark, Python, R, Scala, and other Magellan BI and Reporting tools. A typical process of streaming analytics process involves five steps: Data Acquisition, Data Routing, Streaming Processing, Machine Learning, Prediction Results, and Actionable Insights [https://blogs.opentext.com/streaming-analytics-with-opentext-magellan/].

NiFi is used during the first Data Acquisition steps to collect data from multiple sources such as smart devices, social media, online transactions, and log monitoring. The real-time data can then be combined with other historical data or other data sources before being feed into downstream system [https://blogs.opentext.com/streaming-analytics-with-opentext-magellan/]. Data is then being streamed by Kafka in Data Routing step and then being read and applied business rules by Spark Streaming API before it is being store in data lake. Spark Streaming API will apply machine learning prediction model in Machine Learning step and then being saved in Prediction Results. One the result is created, organizations can take quick decisions to provide business benefits and insights.

As a result, Mallegan was able to create a low cost solutions that has the flexibility and extensibility of open source software. 

### Real Time Streaming at Xenonstack
https://www.xenonstack.com/blog/big-data-engineering/real-time-streaming-apache-spark-nifi-and-kafka/

### Social Competitive Intelligence Application at Compose
Compose is an IBM company launched in 2010 that offer databases as a service on the cloud that are production ready and are easy to manage. NiFi in being used in Compose as part of their Competitive Intelligence infrastructure that involves other software such as Twitter, IBM Watson, Redis, and MongoDB. NiFi was used to extract filtered Twitter Stream data and attributes and send tweet data to IBM Watson for Sentiment analysis, as well as updating Redis for dashboards and reporting purpose and at the same time store all data in MongoDB [http://mybbt.bbtconsulting.com:8069/slides/slide/a-real-use-case-with-nifi-the-swiss-army-knife-of-data-flow-121] . 

 
## Conclusion
 
## Acknowledgement
 
## Notes (not inlcuded)

I think we need to move any citations over to https://github.com/cloudmesh-community/fa18-523-56/blob/master/paper/paper.bib ??
Batch vs Live stream (Live)
 
Theory
Implementation (e.g. Python)
Benchmark
A more detailed outline is
Paper
Title
Abstract
Introductions
Requirements
Architecture
Implementation
Benchmark
Conclusions
Bibliography
Work breakdown

