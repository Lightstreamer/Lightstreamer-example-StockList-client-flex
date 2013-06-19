
Lightstreamer StockList Demo Client for Adobe Flex SDK
======================================================

This project includes different demos for Adobe Flex SDK based on Lightstreamer StockList Adapter:

* Flex :: Stock-List Demo
* AIR  :: Stock-List Demo (To be add)

Flex :: Stock-List Demo
-----------------------

<table>
  <tr>
    <td style="text-align: left">
      &nbsp;<a href="http://www.lightstreamer.com/demo/Flex_StockListDemo/" target="_blank"><img src="http://www.lightstreamer.com/img/demo/screen_flex.png"></a>&nbsp;
      
    </td>
    <td>
      &nbsp;An online demonstration is hosted on our servers at:<br>
      &nbsp;<a href="http://www.lightstreamer.com/demo/Flex_StockListDemo/" target="_blank">http://www.lightstreamer.com/demo/Flex_StockListDemo/</a>
    </td>
  </tr>
</table>

This is a Flex version of the [Stock-List Demos](https://github.com/Weswit/Lightstreamer-example-StockList-client-javascript), where ten items are subscribed to.<br>
This app uses the <b>Flex Client API for Lightstreamer</b> to handle the communications with Lightstreamer Server and uses the <b>Flex DataGrid</b> to display the real-time data pushed by Lightstreamer Server.<br>
The upper table shows the automatic binding of a Lightstreamer data table to a Flex widget (a DataGrid). You can sort on any columns and drag the columns around. The buttons to the right control the update highlight effects and can stop/start the subscription.

The lower table shows the direct use of pushed values to manually update a Flex widget (a TextArea). The buttons to the right can clear the TextArea and stop/start the subscription.

Tables involved:
* A [VisualTable](http://www.lightstreamer.com/docs/client_flex_asdoc/com/lightstreamer/as_client/VisualTable.html) containing 10 items, subscribed to in <b>MERGE</b> mode, bound to the Flex DataGrid.
* A [NonVisualTable](http://www.lightstreamer.com/docs/client_flex_asdoc/com/lightstreamer/as_client/NonVisualTable.html) containing 10 items, subscribed to in <b>MERGE</b> mode, used to get the events to write into the Flex TextArea.


Build and Run
-------------

The /Flex4_StockListDemo folder of this project is comprised of the following folders:

* /src<br>
  Contains the sources to build the Flex application.

* /lib<br>
  Should contain the Lightstreamer library to be used for the build process.<br>
  Please, download the [Lightstreamer distribution](http://www.lightstreamer.com/download) and copy the Lightstreamer_as_client.swc file from the Lightstreamer Flex Client SDK (that is located under the DOCS-SDKs/sdk_client_flex/lib folder) into this folder of the project.

* /deploy<br>
  Contains a deployment image of the demo, which includes a container page and other web resources. You have to complete this by adding in the deploy/Flex4_StockListDemo folder the swfobject.js version 2.2 file form [SWFObject 2](http://code.google.com/p/swfobject/downloads/list) and the built Flex application (Flex4StockListDemo.swf).
  This deployment image is ready to be deployed under Lightstreamer's internal Web Server, by copying all the contents into the "pages" directory.

By the current configuration, the demo tries to access Lightstreamer Server by using the protocol, hostname and port from which the "index.html" page was requested; in other words, the demo assumes that the static resources are deployed inside Lightstreamer Server.<br>
In order to deploy the demo static resources on an external Web Server, some changes are needed on the deployment image before or after copying it into the Web Server folders.
The configuration of the hostname and port (and maybe the protocol) to be used to access Lightstreamer Server should be changed. The configuration lines can be easily found at the beginning of the "index.html" file and can be modified manually, without the need for a recompilation.<br>
Then, in order to allow the page to get resources from a different server, the Web Server address has to be included in the "/crossdomain.xml" file deployed under Lightstreamer Server.
See the <flex_crossdomain_enabled> element in the Server configuration file for details.

Anyway the [QUOTE_ADAPTER](https://github.com/Weswit/Lightstreamer-example-Stocklist-adapter-java) and [LiteralBasedProvider](https://github.com/Weswit/Lightstreamer-example-ReusableMetadata-adapter-java) have to be deployed in your local Lightstreamer server instance. The factory configuration of Lightstreamer server already provides this adapter deployed.<br>
The demos are now ready to be launched.

See Also
--------

* [Lightstreamer StockList Demo Client for JavaScript](https://github.com/Weswit/Lightstreamer-example-Stocklist-client-javascript)
* [Lightstreamer StockList Demo Adapter](https://github.com/Weswit/Lightstreamer-example-Stocklist-adapter-java)
* [Lightstreamer Reusable Metadata Adapter in Java](https://github.com/Weswit/Lightstreamer-example-ReusableMetadata-adapter-java)

Lightstreamer Compatibility Notes
---------------------------------

- Compatible with Lightstreamer JavaScript Client library version 6.0 or newer.