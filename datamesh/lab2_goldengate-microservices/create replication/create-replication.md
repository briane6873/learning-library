# Setup of GoldenGate Microservices for Replication

## Introduction

This hands-on lab is designed to demonstrate how Oracle GoldenGate 19c Microservices can be used to setup a replication environment by a mix of web page, shell scripts and Rest API interfaces.  

The labs will walk the end-user through how to add components of Oracle GoldenGate replication.

*Estimated Lab Time*: 30 mins

### About Oracle GoldenGate Microservices
Oracle GoldenGate offers high-performance, fault-tolerant, easy-to-use, and flexible real- time data streaming platform for big data environments. It easily extends customers’ real-time data integration architectures to big data systems without impacting the performance of the source systems and enables timely business insight for better decision making. This workshop focuses on **GoldenGate Real Time Data Capture** demonstrating four scenarios that you can use (both on-premise and in the cloud) to capture real time data changes from your sources.

### Lab Architecture

![](./images/ggmicroservicesarchitecture.png " ")

### Objectives

The objectives of the lab is to familiarize you with the process to create data replication objects that will allow you to replicate data realtime using GoldenGate Microservices while leveraging RestfulAPIs.

### Prerequisites
This lab assumes you have:
- A Free Tier, Paid or LiveLabs Oracle Cloud account
- You have completed:
    - Lab: Prepare Setup (*Free-tier* and *Paid Tenants* only)
    - Lab: Environment Setup
    - Lab: Initialize Environment

In this lab we will review the GoldenGate Microservices Extract and insert records into the source database Truck_Stream


## Task 1: Set up environment to populate truck streaming.

1. sign into the data integration server

2. Click on *Terminal* icon on the desktop to start a terminal session


![](./images/terminal1.png " ")


3. [oracle@dmsageintegration ~]$ cd scripts


![](./images/truckstream2.png " ")

sudo into oracle user

```
<copy>sudo su - oracle

```
```
<copy>
cd /home/oracle
</copy>
```
5. change directory to scripts

```
<copy>
oracle@dmsageintegration$ cd scripts/
</copy>
```

6. cat the setEnv shell script

```
<copy>cat setEnv.sh
```
7. copy and paste export lines to terminal . Press enter to set up environment


![](./images/terminal2.png " ")
This will set up the Oracle environment


## Task 2: Run commands to populate Truck Stream inserts 


1. [oracle@dmsageintegration ~]$ cd ..


2.  run script to generate records in TruckStream database

```
<copy> cd ..
```

3. Run script to populate Truck Stream database with inserts

```
<copy>sh ./scripts/feed_integration_script.sh ./scripts/TruckStreamScript2.sql 1
```


![](./images/truckstream3.png " ")

## Task 3: Review GoldenGate Microservices Deployment Extract – "EXT2"


Deployments are a new concept in Oracle GoldenGate Microservices.
Deployments provide a siloed approach to splitting replication environments between applications, customers, or environments. This allows for greater control over the use of Oracle GoldenGate in larger environments. In this case, we are deploying an extract to write to GG Stream Analytics.


**GoldenGate Extracts** define the rules and parameters for replicating data from the Truck Stream Oracle Database real time to load into the GG Stream Architecture

## Task 4: Sign Into GoldenGate Microservices Console

1. On the web browser window on the right preloaded with *Oracle GoldenGate Administrator Manager*, click on the *Username* field and provide the credentials below to login.


![](./images/goldengate-login.png " ")


2. Confirm successful login. Verify green checkbox that extract is running successfully for EXT2

![](./images/ggma2.png " ")

3. Review GoldenGate Extract from Database - **Truck Stream**. 


![](./images/ggma3.png " ")

4. Select **Action / Details** from the drop down. 

![](./images/ggma4.png " ")

5. Confirm inserts by selecting **statistics**. 

![](./images/ggma_ext.png " ")

6. Review parameter file - Table being extracted is DATAINT.TRUCK_STREAM


## Summary
The objectives of the lab was to familiarize you with the process to create data replication objects that will allow you to replicate data real-time using GoldenGate Microservices.

Oracle GoldenGate offers high-performance, fault-tolerant, easy-to-use, and flexible real- time data streaming platform. It easily extends customers’ real-time data integration architectures without impacting the performance of the source systems and enables timely business insight for better decision making.

You may now [proceed to the next lab](#next).

## Learn More

* [GoldenGate Microservices](https://docs.oracle.com/en/middleware/goldengate/core/19.1/understanding/getting-started-oracle-goldengate.html#GUID-F317FD3B-5078-47BA-A4EC-8A138C36BD59)

## Acknowledgements
* **Author** - Brian Elliott, Data Integration, August - 2022
* **Contributors** - Brian Elliott, Data Integration, August - 2022 
- **Last Updated By/Date** - Brian Elliott, Data Integration, August - 2022
