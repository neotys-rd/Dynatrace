# Dynatrace OneAgent	

## Overview

This bundle of advanced actions allows you to integrate [NeoLoad](https://www.neotys.com/neoload/overview) and Dynatrace OneAgent to improve the analysis of a load testing test.

This bundle has the following actions:  

* **DynatraceEvents**
  Links a load testing event to all services used by an Application monitored by Dynatrace  
  
* **DynatraceMonitoring**   
    * **Dynatrace -> NeoLoad**: Retrieve Infrastructure and Services metrics from DynaTrace and insert them in NeoLoad External Datas so that
      you can correlate NeoLoad and DynaTrace metrics within NeoLoad.
    * **NeoLoad -> Dynatrace**: Send the global statistics of the test to Dynatrace OneAgent so that it can be used as custom metrics 
      in Dynatrace dashboards.
      
     
| Property | Value |
| -----| -------------- |
| Maturity | Experimental |
| Author   | Neotys Partner Team |
| License  | [BSD Simplified](https://www.neotys.com/documents/legal/bsd-neotys.txt) |
| NeoLoad  | 6.1 (Enterprise or Professional Edition w/ Integration & Advanced Usage and NeoLoad Web option required)|
| Requirements | NeoLoad Web SaaS subscription |
| Bundled in NeoLoad | No
| Download Binaries | See the [latest release](https://github.com/Neotys-Labs/Dynatrace/releases/latest)

## Installation

1. Download the [latest release](https://github.com/Neotys-Labs/Dynatrace/releases/latest)
1. Read the NeoLoad documentation to see [How to install a custom Advanced Action](https://www.neotys.com/documents/doc/neoload/latest/en/html/#25928.htm)

## Set-up

Once installed, how to use in a given NeoLoad project:

1. Create a User Path “Dynatrace”
1. Insert DynatraceEvents in the ‘End’ block.
1. Insert DynatraceMonitoring in the ‘Actions’ block.
1. Create a Population “Dynatrace” that contains 100% of User Path “Dynatrace”
1. In the Runtime section, select your scenario, select the “Dynatrace” population and define a constant load of 1 user.

## Parameters for Dynatrace Events

| Name             | Description |
| -----            | ----- |
| Dynatrace_ID     |  Id of your saas dynatrace environment (http://<id>.live.dynatrace.com) |
| Dynatrace_API_KEY| API key of your dynatrace account |
| Tags (optional)  | Dynatrace Tags of the services used by your SUT |
| EventStatus      |: status sent to dynatrace : START or STOP |
| Dynatrace_Managed_Hostname (Optional) | Hostname of your dynatrace managed environment |

## Parameters for Dynatrace Monitoring

Tip: Get NeoLoad API information in NeoLoad preferences: Project Preferences / REST API.

| Name             | Description |
| -----            | ----- |
| Dynatrace_ID     |  Id of your saas dynatrace environment (http://<id>.live.dynatrace.com) |
| Dynatrace_API_KEY| API key of your dynatrace account |
| Tags (optional)  | Dynatrace Tags of the services used by your SUT |
| EventStatus      |: status sent to dynatrace : START or STOP |
| Dynatrace_Managed_Hostname (Optional) | Hostname of your dynatrace managed environment |
| NeoLoadAPIHost   | IP address or Host of the DataExchange API |
| NeoLoadAPIport   | Port of the NL DataExchange API   |
| NeoLoadKeyAPI    | API key of the DataExchange API   |
  
## Status Codes

* NL-DynatraceMonitoring_ERROR: Issue while monitoring dynatrace  
* NL-DynatraceEvent_ERROR: Error while sending the event to dynatrace  


