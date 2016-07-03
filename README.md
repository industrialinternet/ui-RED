**ui-RED**

A Web UI and server-side framework for the brilliant Node-RED IoT platform

ui-RED is a light weight framework used to build WebUIs/Dashboards for Things & time-series data.
ui-RED is built entirely in Node-RED on the server side. And on the client standard HTML, CSS, JS & SVG two using two libraries Jquery and Highcharts (graphs & gauges). It looks to build on the power and ease of integration of the Node-RED platform.

We’ve attempted to make the framework as simple as possible.
With the hope that inquisitive NRers will explore and learn.
And then develop their own widgets and Web Apps.
To that end we have avoided using modern client-side frameworks such as Angular.js.
In fact many will find our client side bindings very Old Hat, this is intentional!

ui-RED is based on a simple JSON definitions and data store which we call Datapoints.
Which provides meta data, curent and cached data for the UI.
The cache is file based and should be kept shallow (e.g. Max 100 records per data point).
And is needed to render Spark & Graph widgets on page load and for calculating averages etc.
 
UI templates are built in HTML and  mustache {{ tags }} and use javascript functions to create HTML widgets and client side javascript. For example to render a Highchart Gauge for datapoint 10 two tags are needed
{{#renderGauge}}{{dp10}}{{/renderGauge}} for HTML and {{#jsGauge}}{{dp10}}{{/jsGauge}} for javascript.

The core the framework is the Datapoint this defines what and how inputs to the UI are handled.
A main datapoint handler function maps in-bound sensor & IO data to datapoint store.
The framework comes with a built-in Datapoint editor.
We've also built a simple UI simulator Web App to allow NRers to explore the framework.

To be of real use ui-Red on Node-RED needs to run all the time.
This is to ensure that the Datapoint cache is kept up to date.

**known issues**

ui-RED is very Beta and there are still a large number of issues.
ui-RED is NOT production grade!
We hope to lanuch in early fall of 2016.

**Concepual Node-RED flow**

![ScreenShot](https://github.com/industrialinternet/ui-RED/blob/master/ui-red-v001.png)

**Node-RED flow**

![ScreenShot](https://github.com/industrialinternet/ui-RED/blob/master/ui-RED-flow-v3.png)

**ui-Red Node-RED subflow**  ui-RED has authentication using bcryp but this needs re-factoring and UI adding to make it easy to use.

![ScreenShot](https://github.com/industrialinternet/ui-RED/blob/master/ui-RED-sub-flow-v3.png)

**ui-Red Node-RED to -> Web client handlers & css**

![ScreenShot](https://github.com/industrialinternet/ui-RED/blob/master/Ui-red-client-03.png)

**Datapoint Editor**

![ScreenShot](https://github.com/industrialinternet/ui-RED/blob/master/ui-RED-dp-editor.png)

**Example UI**

![ScreenShot](https://github.com/industrialinternet/ui-RED/blob/master/ui-red.png)

**Charts**  Spark lines on screen shot above and most charts are initially populated from persisted historical data and then updated in real-time from there on. The osio chart uses the opensensor.io historical API.

![ScreenShot](https://github.com/industrialinternet/ui-RED/blob/master/uired-osio-hist.png)

