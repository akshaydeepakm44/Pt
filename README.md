## FLW Application Load Testing

This repository contains load testing scripts for the FLW application created using Apache JMeter.
A separate branch named load-test has been created specifically for performance testing activities.

## Overview

The load testing scripts simulate multiple users interacting with the FLW application APIs to evaluate system performance under concurrent usage.

## Key points:
Load testing is performed using Apache JMeter
Test data is supplied using a CSV Data Set Config
The CSV file contains multiple user credentials used during the test execution
The test collection includes APIs such as login, user retrieval, beneficiary data, registration, tracking, and other application workflows

## The goal of these tests is to analyze:

Response time
Throughput
Error percentage
System behavior under concurrent load


## This load-test branch contains:

JMeter test plan (.jmx)
CSV dataset for user credentials

Prerequisites
Before running the test locally, ensure the following tools are installed:
Apache JMeter (version 5.x or later)
Git
Java (JDK 8 or above)

You can verify installations using:
java -version
jmeter -v
git --version

## How to Clone the Repository

Clone the repository using the following command:
```
git clone <repository-url>
```

Navigate to the project directory:
```
cd your-repository-name
```

Switch to the load-test branch:
```
git checkout load-test
```
## Running the Load Test Locally
## Step 1: Open JMeter
Launch Apache JMeter.

## Step 2: Open the Test Plan
Open the .jmx file located in the repository:

File → Open → select the JMeter test plan (.jmx)

## Step 3: Verify CSV Dataset
Ensure the CSV Data Set Config is correctly pointing to the dataset file containing user credentials.

## Step 4: Run the Test
Click the Start (▶) button in JMeter to begin executing the load test.

## Step 5: View Results
You can monitor results using:
View Results Tree
Summary Report
