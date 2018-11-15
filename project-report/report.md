# Apache NiFi Chapter :hand: fa18-523-56

| Daniel Hinders
| dhinders@iu.edu
| Indiana University
| hid: fa18-523-56
| github: [:cloud:](https://github.com/cloudmesh-community/fa18-523-56/blob/master/project-report/report.md)
| code: [:cloud:](https://github.com/cloudmesh-community/fa18-523-56/blob/master/project-code/code)

**:mortar_board: Learning Objectives**

* Learn about NIFI
* Install NIFI and setup a data stream with various processors
---

Keywords: ETL, Data Stream, NiFi, NSA, 


## Apache NiFi Introduction
![NiFi Architecture](images/nifi_architecture.PNG)
{#fig:nifiarchitecture}

## NiFi History

## NiFi Features

## NiFi Architecture

## Install NiFi


### Apache NiFi - Windows

(Note: Assumes a recent verison of JAVA is installed)

**1**
NiFi can be downloaded from Apache NiFi homepage[@fa18-523-56-nifi-download-page]. Select the latest version and the bin.zip option for the Windows instillation.

![nifi_download](images/nifi_download.png)

{#fig:nifi_download}

**2**
Unzip the install package.

**3**
Navigate to the configuration directory:
``` 
nifi-1.8.0-bin\nifi-1.8.0\conf
```
![nifi_config](images/nifi_config.png)

{#fig:nifi_config}

Open nifi.properties file with a text editor and edit nifi.web.http.port= to the desired port

![nifi_properties](images/nifi_properties.png)
{#fig:nifi_properties}

**4**
Start up NiFi by navigating to
``` 
nifi-1.8.0-bin\nifi-1.8.0\bin
```
![nifi_bin](images/nifi_bin.png)
{#fig:nifi_bin}
Run the windows batch file
``` 
run-nifi.bat
```
Wait about 5 minutes for NiFi to load

**5**

Open the NiFi GUI by opening a browser and navigate to
```
http://localhost:9090/nifi
```
![nifi_nifihome](images/nifi_nifihome.png)
{#fig:nifi_nifihome}

## Building a Basic NiFi Flow

**1**

Click and drag the processor icon fron the top tray to add a processor.
You will be able to select from hundreds of processosrs.
Type into the filter "tail" and select the TailFile processor and click "ADD"

![nifi_processor_tailfile](images/nifi_processor_tailfile.png)
{#fig:nifi_processor_tailfile}

### Log File Tail

### 

## Processors

### Setup Routing Processors

### Setup Data Transformation Processors

### Setup Database Access Processors

### Setup System Integration Processors

### AWS Processors

## What is NIFI good for
### source to analytic platform
### 

## What is NIFI not good for
### multiple dataset joins
### not good for aggregation  


## Alternatives to NIFI




*Project Structure from piazza*

## Abstract

TBD

## Introduction

TBD

## Requirements

## Design 

## Architecture

## Dataset

## Implementation

## Benchmark

## Conclusion

## Acknowledgement




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


