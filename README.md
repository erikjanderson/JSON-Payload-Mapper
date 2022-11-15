
# JSON Payload Mapper
**Scoped ServiceNow application with a Service Portal UI allowing you to quickly parse through complex JSON objects and generate scripts to easily flatten them**

![](Docs/Payload%20Mapper%20%28JSON%20Convert%29.png)

I've spent a fair bit of time building API based 3rd party integrations into ServiceNow. And one of the most tedious, and error prone parts of doing this is when you get the jumbled up mess of a JSON payload from the API and then you need to go through and parse it and flatten it so that it can be cleanly inserted into staging tables. Its really easy to forget a null checking if statement resulting in the "cannot read property of undefined" error and you want to make sure that the property names that you are setting are clear and easy to understand. The JSON Payload Mapper is designed to automate a lot of this.

In this app you can do the following:
 1. Analyze a raw JSON payload from the API.
 2. Select which payload properties you want to extract.
 3. Set key identifiers in the payload.
 4. Modify the target model.
 5. Generate and and copy the usage script so that the any payload of the same structure can be flattened in a repeatable and consistent way.

## How to get
You can get this tool by either forking this branch and importing it to your own instance, or you can download the repository and import the update set manually.
**NOTE: This tool is not meant for production use. The idea is to have this tool in a sub production instance or even a PDI so that you can quickly generate the script that you need and then move the script itself over to the application that needs it.**

## Payload Mapper Overview
Once installed, the payload mapper can be accessed under **JSON Payload Mapper > Payload Mapper**. This will load the Payload Mapper custom Service Portal page. 

Immediately after loading, a modal popup will ask you to select a map you want to edit. Maps can be saved and in system properties in the event that you want to make edits to them later on. If you are just doing this as a one time thing, the "Mapless" option will allow you to do everything besides saving the map.
![](Docs/Payload%20Mapper%20%28Map%20Select%29.png)

If you select the mapless option or this is the very first time you are configuring a map, the modal will then ask you to add feed it an example payload so that it can generate the necessary UI components for you to get started. This payload can either be a single JSON object or an entire array of objects. Paste the payload in the text area and click the Analyze button.

![](Docs/Payload%20Mapper%20%28Map%20Select%20Outline%29.png)

Form Overview

 1. Search Bar: Useful when dealing with large payloads with a lot of poperties. Filters the Oject Schema view below.
 2. Save Map Button: Allows you to save changes made to the mapping. Not available if using the mapless map option.
 3. Advanced Options Button: Opens the list of advanced options.
 4. Name of the current map
 5. Schema view: Shows an intented view of the scanned object making it easier to see the overall strucutre of the object including types and the ability to collaps individual sections.
 6. Model Editor Section: Allows you to modify the property names when they are converted into a flattened object.

