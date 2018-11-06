Welcome to DataStax Developer Day
========================================

In this repository, you'll find everything from the DataStax Developer Day event. There are materials used during presentations, hands-on exercises and reference applications. Feel free to bookmark this page for future reference!

<img src="./img/DeveloperDayBanner.png" height="200" />

## Sessions

#### Cassandra Track
| Time  | Title
|---|---|
| 10:30 AM - 12:15 PM  | [Core Cassandra](https://github.com/DataStax-Academy/developer-day-2018/blob/master/slides/Developer%20Day%20-%20Core%20Cassandra.pdf)  |
| 01:00 PM - 02:45 PM | [Cassandra Data Modeling](https://github.com/DataStax-Academy/developer-day-2018/blob/master/slides/Developer%20Day%20-%20Data%20Modeling.pdf)  |
| 03:00 PM - 04:45 PM | [Cassandra Application Development](https://github.com/DataStax-Academy/developer-day-2018/blob/master/slides/Developer%20Day%20-%20Application%20Development.pdf)  |

#### DSE Track
| Time  | Title
|---|---|
| 10:30 AM - 12:15 PM | [DSE Search](https://github.com/DataStax-Academy/developer-day-2018/blob/master/slides/Developer%20Day%20-%20DSE%20Search.pdf)  |
| 01:00 PM - 02:45 PM | [DSE Analytics](https://github.com/DataStax-Academy/developer-day-2018/blob/master/slides/Developer%20Day%20-%20DSE%20Analytics.pdf)  |
| 03:00 PM - 04:45 PM | [DSE Graph](https://github.com/DataStax-Academy/developer-day-2018/blob/master/slides/Developer%20Day%20-%20DSE%20Graph.pdf)  |

#### Bonus Content
| Time  | Title
|---|---|
| 01:00 PM - 02:45 PM | [DSE Overview](https://github.com/DataStax-Academy/developer-day-2018/blob/master/slides/Developer%20Day%20-%20DSE%20Overview.pdf)  |
| 03:00 PM - 04:45 PM | [DSE Operations & Security](https://github.com/DataStax-Academy/developer-day-2018/blob/master/slides/Developer%20Day%20-%20Operations%20&%20Security.pdf)  |

## Hands-On Exercises

#### Instructions
* [Install DataStax Enterprise](https://docs.datastax.com/en/install/doc/install60/installTOC.html)

Or use Docker :
```
docker run -e "DS_LICENSE=accept" -it -d -p 9042:9042 --name dse datastax/dse-server -s -g
```

* [Install DataStax Studio](https://docs.datastax.com/en/install/doc/install60/installStudio.html)
   - The notebooks below should be [imported](https://docs.datastax.com/en/studio/6.0/studio/importNotebook.html) and opened in DataStax Studio

Or use Docker :
```
docker run -e "DS_LICENSE=accept" -it -d -p 9091:9091 --link dse:dse datastax/dse-studio
```

#### Core Cassandra
| Notebooks | Setup Notes
|---|---|
| [Core Cassandra First Touch](https://github.com/DataStax-Academy/developer-day-2018/blob/master/notebooks/Core_Cassandra_First_Touch.studio-nb.tar) | - Data should be [loaded](https://github.com/DataStax-Academy/developer-day-2018/tree/master/setup/load-data) in the `killrvideo` keyspace.
| [Core Cassandra Data Loading](https://github.com/DataStax-Academy/developer-day-2018/blob/master/notebooks/Core_Cassandra_Data_Loading_DataStax_Developer_Day.studio-nb.tar) | - Data should be [loaded](https://github.com/DataStax-Academy/developer-day-2018/tree/master/setup/load-data) in the `killrvideo` keyspace.<br> - Uses the file **movies.csv**, located in this repo under `data/csv/movies.csv`.
| [Core Cassandra Data Availability](https://github.com/DataStax-Academy/developer-day-2018/blob/master/notebooks/Core_Cassandra_Data_Availability_DataStax_Developer_Day.studio-nb.tar) | - This notebook exercise can only be done with a three-node DSE cluster.<br> - Recommended to drop the `killrvideo` keyspace, if it exists.<br>- Uses a hard-coded datacenter `DC1`; replace that with your own datacenter name, where needed.<br> - Install and setup [DataStax OpsCenter](https://docs.datastax.com/en/install/doc/install60/opscInstallOpsc.html) to monitor your cluster.

#### DSE Search
| Notebooks | Setup Notes
|---|---|
| [Search Queries](https://github.com/DataStax-Academy/developer-day-2018/blob/master/notebooks/DSE_Search_Search_Queries_DataStax_Developer_Day.studio-nb.tar) | - Needs the Search [workload enabled](https://github.com/DataStax-Academy/developer-day-2018/tree/master/setup/enable-workload).<br>  - Data should be [loaded](https://github.com/DataStax-Academy/developer-day-2018/tree/master/setup/load-data) in the `killrvideo_search` keyspace.
| [Text Search](https://github.com/DataStax-Academy/developer-day-2018/blob/master/notebooks/DSE_Search_Text_Search_DataStax_Developer_Day.studio-nb.tar) | - Needs the Search [workload enabled](https://github.com/DataStax-Academy/developer-day-2018/tree/master/setup/enable-workload).<br> - Data should be [loaded](https://github.com/DataStax-Academy/developer-day-2018/tree/master/setup/load-data) in the `killrvideo_search` keyspace.

#### Cassandra Data Modeling
| Notebooks | Setup Notes
|---|---|
| [Intro](https://github.com/DataStax-Academy/developer-day-2018/blob/master/notebooks/Data_Modeling_Data_Modeling_Intro_DataStax_Developer_Day.studio-nb.tar) | - Data should be [loaded](https://github.com/DataStax-Academy/developer-day-2018/tree/master/setup/load-data) in the `killrvideo` keyspace.
| [Cassandra-Land Project](https://github.com/DataStax-Academy/developer-day-2018/blob/master/notebooks/Data_Modeling_Cassandra-Land_Project.studio-nb.tar) | - Data should be [loaded](https://github.com/DataStax-Academy/developer-day-2018/tree/master/setup/load-data) in the `killrvideo` keyspace.

#### DSE Analytics
| Notebooks | Setup Notes
|---|---|
| [Intro](https://github.com/DataStax-Academy/developer-day-2018/blob/master/notebooks/DSE_Analytics_Intro_DataStax_Developer_Day.studio-nb.tar) | - Needs the Analytics [workload](https://github.com/DataStax-Academy/developer-day-2018/tree/master/setup/enable-workload) and [Always-On SQL](https://github.com/DataStax-Academy/developer-day-2018/blob/master/setup/enable-AOSS) enabled.<br> - Data should be [loaded](https://github.com/DataStax-Academy/developer-day-2018/tree/master/setup/load-data) in the `killrvideo` keyspace.
| [ETL](https://github.com/DataStax-Academy/developer-day-2018/blob/master/notebooks/DSE_Analytics_ETL.studio-nb.tar) | - Needs the Analytics [workload](https://github.com/DataStax-Academy/developer-day-2018/tree/master/setup/enable-workload) and [Always-On SQL](https://github.com/DataStax-Academy/developer-day-2018/blob/master/setup/enable-AOSS) enabled. <br> - Data should be [loaded](https://github.com/DataStax-Academy/developer-day-2018/tree/master/setup/load-data) in the `killrvideo` keyspace.
| [DataFrames](https://github.com/DataStax-Academy/developer-day-2018/blob/master/notebooks/DSE_Analytics_DataFrames_DataStax_Developer_Day.studio-nb.tar) | - Needs the Analytics [workload enabled](https://github.com/DataStax-Academy/developer-day-2018/tree/master/setup/enable-workload). <br> - Data should be [loaded](https://github.com/DataStax-Academy/developer-day-2018/tree/master/setup/load-data) in the `killrvideo` keyspace.

#### DSE Application Development
| Notebooks | Setup Notes
|---|---|
| [Prepared Statements](https://github.com/DataStax-Academy/developer-day-2018/blob/master/notebooks/DSE_Application_Development_Prepared_Statements.studio-nb.tar) | - The [KillrVideo reference app](https://killrvideo.github.io/docs/languages/java/) should be set up using the `app-dev-days-exercises` branch.
| [Accessors](https://github.com/DataStax-Academy/developer-day-2018/blob/master/notebooks/DSE_Application_Development_Accessors.studio-nb.tar) | - The [KillrVideo reference app](https://killrvideo.github.io/docs/languages/java/) should be set up using the `app-dev-days-exercises` branch.

#### DSE Graph
| Notebooks | Setup Notes
|---|---|
| [DSE Graph DataStax Developer Day](https://github.com/DataStax-Academy/developer-day-2018/blob/master/notebooks/DSE_Graph_DataStax_Developer_Day.studio-nb.tar) | - Needs the Graph and Search workload enabled. <br> - A warning message will pop out when you open the notebook saying the graph hasn't been created. Click on the button to create the graph.<br> - The location to the KillrVideo.kryo file in Step 3 should be edited to point to its location in your local repo, under `data/graph/KillrVideo.kryo`.
| [DSE Graph DataStax Developer Day with answers](https://github.com/DataStax-Academy/developer-day-2018/blob/master/notebooks/DSE_Graph_DataStax_Developer_Day_with_answers.studio-nb.tar) | - Needs the Graph and Search workload enabled. <br> - A warning message will pop out when you open the notebook saying the graph hasn't been created. Click on the button to create the graph.<br> - The location to the KillrVideo.kryo file in Step 3 should be edited to point to its location in your local repo, under `data/graph/KillrVideo.kryo`.

#### DSE Operations & Security
| Notebooks | Setup Notes
|---|---|
| [Installing DSE](https://github.com/DataStax-Academy/developer-day-2018/blob/master/notebooks/DSE_Operations_Security_Installing_DSE_DataStax_Developer_Day.studio-nb.tar) | - Needs three separate instances, [DSE binary tarball](https://docs.datastax.com/en/install/doc/install60/installTARdse.html#installTARdse__specific60version), and [DataStax OpsCenter](https://docs.datastax.com/en/install/doc/install60/opscInstallOpsc.html).<br> - Scripts mentioned in the exercise are not available since they are specific to DataStax environments.
| [Securing DSE](https://github.com/DataStax-Academy/developer-day-2018/blob/master/notebooks/DSE_Operations_Security_Securing_DSE_DataStax_Developer_Day.studio-nb.tar) | - Needs a three-node DSE cluster set up by the LifeCycle Manager in [DataStax OpsCenter](https://docs.datastax.com/en/install/doc/install60/opscInstallOpsc.html).<br> - Scripts mentioned in the exercise are not available since they are specific to DataStax environments.

### Extra Materials

* Get involved more tutorials here [DataStax Academy](https://academy.datastax.com/)
* Learn more about [KillrVideo](https://github.com/killrvideo)
* More sample codes [HERE](https://github.com/DataStaxCodeSamples)
