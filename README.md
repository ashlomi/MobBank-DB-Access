
![CDD](https://raw.githubusercontent.com/broadcom/broadcomcdd-datasource/master/screenshots/CA-Broadcom_Horizontal_red-black.png=100x200)
# Broadcom Continuous Delivery Director (CDD) Datasource

This is a Grafana datasource for fetching Metrics from Continuous Delivery Director

## Requirements

Grafana XXXX 

Continuous Delivery Director v8.3 (or above)  or CDD SaaS subscription

## Features

Get release quality continuous testing metrics:
- Total number of test suites
- Total number of successful test suites
- Total number of failed test suites
- Total number of error test suites
- Total number of skipped test suites
- Total number of disabled test suites

query Paraemters:
- Project Name
- Application Name
- Application Nane
- Application Version Name
- Environment Name
- Plugin Name


Select one or more plugin
If a plugin was entered, reply with information on all the plugins

## Configuration

This datasource uses the Instana REST API to query the underlying data services.

First of all you will need to generate an API key (recomanded to use an integration user) 

Configure Retrived values as shown below

![datasource configuration](https://raw.githubusercontent.com/broadcom/broadcomcdd-datasource/main/screenshots/configuration.png)

## Usage
- - - -
### Query Types
The following query types are available:
* <metric name>:

   Use this query type to fetch ccontinuous testing metrics.
   
   
- Total number of test suites
- Total number of successful test suites
- Total number of failed test suites
- Total number of error test suites
- Total number of skipped test suites
- Total number of disabled test suites
   
   
   
* Events

  Use this query type to fetch event data on the devices in your environment.
* Metric

  Use this query type to fetch the performance metrics data of the devices in your environment.

### Query Editor

This section describes the each query editor.

#

This query type requires the following data:

| Field | Description |
|------|-------|
| **Query Type** | Use this field to select the query type |
| **Query** | Use one of the following queries to build a panel. The options for each query type are different **Asset Compliance**, **Policy Compliance** , **Compliance Trend**, **Risk Account**, **Operations**, **Resource Pool** |


### **Events**

The following image displays the Events query type:

![query type](https://raw.githubusercontent.com/broadcom/broadcomcdd-datasource/main/screenshots/events_query.png)

This query type requires the following data:

| Field | Description |
|------|-------|
| **Query Type** | Use this field to select the query type |
| **Query** | Use a Lucene query syntax here |
| **Metric** | Click this field to select a metric for the query. For example, Average, Min, Max, and so on |
| **Group by** | Select a clause to group your data in the panel. |

<br>

### **Metrics**

The following image displays the Metric query type:

![query type](https://raw.githubusercontent.com/broadcom/broadcomcdd-datasource/main/screenshots/metric_query.png)

| Field | Description |
|------|-------|
| **Query Type** | Use this field to select the query type |
| **Metrics** | Add a metrics query to this field.  You can also select an available query form the list. Click the **Metrics** field to view a list of available queries. |
| **Legend** |Add a legend to appear in the panel. You can use a variable here. For example, the value of the {{hostname}} variable is replaced with the host name in the panel. |
| **Min step** | Add a threshold for a lower limit of the Prometheus query. This setting is absolute, and cannot be changed by the value in the **Resolution** field.|
| **Resolution** | Sets the parameter for each pixel to correspond to one data point of a Prometheus range query. Use lower resolutions for better performance.|
| **Format** | Select one of the following formats for the panel: **Time Series** , **Table** , **Heatmap**|
| **Instant** | Use this radio button to return only the latest value for the requested time series. Instant queries return results faster than the normal range queries.|

### **Sample Dashboards**
### Events Dashboard
![events_dashboard](https://raw.githubusercontent.com/broadcom/broadcomcdd-datasource/main/screenshots/events_dashboard.png)

### Metrics Dashboard
![metrics_dashboard](https://raw.githubusercontent.com/broadcom/broadcomcdd-datasource/main/screenshots/metrics_dashboard.png)
