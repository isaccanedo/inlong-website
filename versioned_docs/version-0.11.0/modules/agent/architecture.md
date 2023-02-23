---
title: Architecture
---

## 1. Overview of InLong-Agent
InLong-Agent is a collection tool that supports multiple types of data sources, and is committed to achieving stable and efficient data collection functions between multiple heterogeneous data sources including file, sql, Binlog, metrics, etc.

### The brief architecture diagram is as follows:
![](img/architecture.png)

### design concept
In order to solve the problem of data source diversity, InLong-agent abstracts multiple data sources into a unified source concept, and abstracts sinks to write data. When you need to access a new data source, you only need to configure the format and reading parameters of the data source to achieve efficient reading.

### Current status of use
InLong-Agent is widely used within the Tencent Group, undertaking most of the data collection business, and the amount of online data reaches tens of billions.

## 2. InLong-Agent architecture
The InLong Agent task is used as a data acquisition framework, constructed with a channel + plug-in architecture. Read and write the data source into a reader/writer plug-in, and then into the entire framework.

+ Reader: Reader is the data collection module, responsible for collecting data from the data source and sending the data to the channel.
+ Writer: Writer is a data writing module, which reuses data continuously to the channel and writes the data to the destination.
+ Channel: The channel used to connect the reader and writer, and as the data transmission channel of the connection, which realizes the function of data reading and monitoring


## 3. Different kinds of agent
### 3.1 file agent
File collection includes the following functions:

User-configured path monitoring, able to monitor the created file information
Directory regular filtering, support YYYYMMDD+regular expression path configuration
Breakpoint retransmission, when InLong-Agent restarts, it can automatically re-read from the last read position to ensure no reread or missed reading.

### 3.2 sql agent
This type of data refers to the way it is executed through SQL
SQL regular decomposition, converted into multiple SQL statements
Execute SQL separately, pull the data set, the pull process needs to pay attention to the impact on mysql itself
The execution cycle, which is generally executed regularly

### 3.3 binlog agent
This type of collection reads binlog and restores data by configuring mysql slave
Need to pay attention to multi-threaded parsing when binlog is read, and multi-threaded parsing data needs to be labeled in order
The code is based on the old version of dbsync, the main modification is to change the sending of tdbus-sender to push to agent-channel for integration




