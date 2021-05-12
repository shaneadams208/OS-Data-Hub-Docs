---
id: quickstart
title: Quickstart
description: Get started with the OS Linked Identifiers API
# hide_table_of_contents: true
slug: /os-linked-identifiers-api/quickstart
---

This guide explains how to create an account and get an API key on the OS Data Hub.

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas elementum justo vel tempor ullamcorper. Nullam purus ipsum, interdum ac venenatis non, suscipit ac turpis. Integer congue neque urna, pulvinar dapibus lorem euismod quis. Curabitur convallis commodo ante, eget mattis nibh. Maecenas posuere est vestibulum ante rutrum iaculis sed eu nibh. Nam feugiat vulputate nunc vel placerat. Suspendisse aliquam erat nibh, in tempus velit ultrices sed. Morbi pharetra erat id accumsan interdum. Sed posuere eros et ipsum varius dapibus. Donec nec laoreet neque. Donec non lorem leo. Vestibulum odio orci, aliquam sed tortor eu, consectetur tincidunt risus. Aenean sed porttitor ipsum.


### Instructions to Generate a Project API Key and URL

The following instructions describe how to obtain the API service URL and to generate an API key:

1. Click this link to open the [OS Data Hub](https://osdatahub.os.uk/) in a new tab.
2. Click "API Dashboard" in the main menu.
3. Click "APIs" in the left-hand menu.
4. Click "Add to API project" to the right of OS Vector Tile API.
5. If you already have a project you may choose to add the OS Vector Tile API into that project, or alternatively Select "Add to NEW PROJECT".


Morbi vitae posuere nibh, et venenatis augue. Integer sed neque at augue varius porta. Quisque efficitur felis et bibendum lacinia. Duis enim felis, tristique non gravida non, semper at lorem. Suspendisse potenti. Cras blandit, ligula ut venenatis ultrices, lorem dolor pellentesque urna, vitae rutrum augue dui vitae mi. Quisque eget nisi felis. Ut eget finibus sem.

Maecenas mi neque, pellentesque id aliquet vel, ullamcorper id odio. Nulla eu magna sit amet purus ultricies facilisis. Aliquam eu velit nec mi blandit egestas. Quisque vel magna a dolor vulputate aliquet non eu augue. Donec ac augue et metus feugiat egestas nec eget tortor. Maecenas finibus in erat eget molestie. Quisque sit amet nunc sit amet nibh congue tempus tempus nec ante. Proin non facilisis ipsum. Sed a maximus risus, at laoreet ipsum. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia curae; Aliquam sit amet dolor orci.

Vestibulum vehicula, metus non dapibus congue, sapien turpis fermentum orci, sit amet porttitor magna nulla et nisi. Sed malesuada massa sed lorem ultricies mattis. Ut fringilla odio vel blandit commodo. Morbi et ornare enim. Sed erat nisl, consectetur id dignissim id, convallis ac ante. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Duis vitae vestibulum nulla.


### Instructions to create a web-based application

To do this you will require access to an IDE and to Ordnance Survey’s Github Demo repository. You will not require a Github account in order to access the demos.

Download and install the OSVectorTileAPI repository

1. Navigate to the OS Data Hub demo Github repository which can be found [here](https://github.com/OrdnanceSurvey/OS-Data-Hub-API-Demos).
2. Click the green Clone or download button.

![](../.gitbook/assets/figure1.png)

3. Click the option to Download ZIP.

![](../.gitbook/assets/figure2.png)

4. Navigate to your downloads page and unzip the OSVectorTileAPI folder from the newly downloaded file and place it in your IDE project repository. When you open up your IDE, the new files should appear automatically in your project window.

![](../.gitbook/assets/figure3.png)

5. The folders you have installed contain all the coding required to call and interact with the code libraries. The method differs between IDE, however, to launch the web-based application navigate to, and open the index.html file found in the OpenLayers folder. Once you have done this, run the application.

![](../.gitbook/assets/figure5.png)

### Using the web-based demo

1. Running the project will launch a window in your browser that looks like this:

![](../.gitbook/assets/figure6.png)

The demo application is now running on a temporary local server from your own computer. This sever is private to your IP address and so cannot be shared with other users. This server will exist as long as your IDE is open. You will have to run the index.html file through your IDE each time you wish to use the demo.

2. To use the demo, open up your My projects page on the OS Data Hub and copy the Project API Key.

![](../.gitbook/assets/figure7.png)

3. Paste the key into the Project API Key box on the local server demo and run Load Map.

![](../.gitbook/assets/figure8.png)

This will then generate a fully styled map using the OS Vector Tile API service available for you to now explore. You can also use the code provided in the demo as the basis for your own web-browser application.

**Well done!** You've just completed the following actions:

1. You've obtained the URL and generated an API key for OS Vector Tile API.
2. You've accessed and downloaded the OS Vector Tile API demo from our Github repository.
3. You have created a localised demo using your IDE and have applied your API key in order to interact with the data.

### What next?

For further reading on the OS Vector Tile API, refer to the [technical specification](https://osdatahub.os.uk/docs/vts/technicalSpecification) or check out [code examples](https://labs.os.uk/public/os-data-hub-examples/os-vector-tile-api/).

