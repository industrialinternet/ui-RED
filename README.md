**ui-RED**

A simple Web UI framework for the brilliant Node-RED IoT platform

ui-RED is light weight framework used to build WebUIs/Dashboards for Things & time-series data.
ui-RED is built entirely in Node-RED and only dependant on one external library Highcharts for graphs and gauges.
It looks to build on the brilliance and ease of integration of the Node-RED platform.

We’ve attempted to make the framework as simple as possible.
We hope, allowing inquisitive NRers to develop their own widgets and Web Apps.
To that end we have avoided using modern client side frameworks such as Angular.js.
We use the already installed NR libraries such as Jquery & Fort Awesome.

ui-RED is based on a simple JSON based definition and datastore.
It provides an in-memory and persisted data for the UI.
Persistence is file based and shallow (100 records) and is needed to render widgets on page load.
 
UI templates are built in HTML and  mustache {{ tags }} and use javascript helper functions to create widgets.
To render the HTML for a Highchart gauge this line for datapoint 10 is all that is needed.
{{#renderGauge}}{{#dp10}}dp10::{{tag}}::{{des}}::{{v}}::{{unit}}{{/dp10}} {{/renderGauge}}

The core the framework is the Datapoint this defines what and how inputs to the UI are handled.
The framework comes with a built-in Datapoint editor and simple UI simulator web App to allow NRers to explore the framework.

To be of real use ui-Red on Node-RED needs to run all the time.
This is to ensure that the all Datapoints are kept up to date. 

**Issues**

ui-RED is very Alpha and there are still a large number known issues.
Such as responsive deign errors & web client getting out of sync.
ui-RED is NOT and nowehere near product grade.

**Concepual Node-RED flow**

![ScreenShot](https://github.com/industrialinternet/ui-RED/blob/master/ui-red-v001.png)

**Node-RED flow**

![ScreenShot](https://github.com/industrialinternet/ui-RED/blob/master/ui-red-nr-flow.png)

**ui-Red Node-RED subflow**  ui-RED has authentication using bcryp but this needs re-factoring and UI adding to make it easy to use.

![ScreenShot](https://github.com/industrialinternet/ui-RED/blob/master/ui-red-subflow.png)

**Example UI**

![ScreenShot](https://github.com/industrialinternet/ui-RED/blob/master/ui-red.png)

**Charts**  Spark lines on screen shot above and most charts are initially populated from persisted historical data and then updated in real-time from there on. The osio chart uses the opensensor.io historical API.

![ScreenShot](https://github.com/industrialinternet/ui-RED/blob/master/uired-osio-hist.png)

