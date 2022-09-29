# WestFax API Postman collection

![WESTFAX](https://westfax.com/img/WestFax_Logo.webp)

### WestFax API

The WestFax API is comprised of a large set of methods that are exposed using a RESTful interface.  Data can be interchanged in a number of formats including JSON and XML.  Additionally, WestFax offers SOAP and RPC bindings that are described elsewhere.  For the purposes of this document and the SDK, the REST interface with JSON encoding is used.  WestFax hosts the API servers in its dedicated and secure datacenters, providing robust and fault tolerant access to our Cloud Fax API.

### Purpose

The purpose of this document and the associated Postman collection and environment files is to demonstrate the functionality of WestFax’s API methods for an API implementation.  The Postman (https://www.getpostman.com/) collection and environment files can be imported into the Postman tool which can then be used to call WestFax’s API methods and see their raw responses. In conjunction with this Postman collection, WestFax has published an SDK and Demo program that demonstrates the main workflow of the API.  (https://github.com/westfax/SDK-Fax)  

### About the Postman Collection

The WestFax Postman collection contains all of the API methods that are needed to start faxing. API methods ranging from authentication and pulling general account information to sending and receiving faxes are all in this postman collection.

The Postman collection was designed to mirror the WestFax SDK Demo and mirrors the workflow of the API. All of the API methods in this postman collection are the same ones that are used in the raw interface code file in the WestFax SDK.

### Using the Postman Collection

The Postman collection is a tool that shows the use of the API methods.  Postman allows the user to see the URL being posted to, the parameters being sent, and the API’s response for each API method. The collection contains various aspects from authentication, to Account, Product, User and Contact discovery to Sending and Receiving Faxes. 

#### Importing the Collection 

In the upper left hand side of the Postman tool, there is an “import” button. After clicking the “import” button, drag and drop the WestFaxApi_Postman_collection.json file and the WestFaxApiEnvironment.postman_environment.json file into the drop area or browse for the files.

#### Configuration

In the top right of the postman tool, there is a button with an eye on it. After clicking the button with an eye, a drop down should show some predefined variables. In the top right of the drop down there is an “edit” link where the current values of the variables can be changed. Update the “User” variable with your account username, the “Pass” variable with your password, and the “ProdId” variable with your ProductId.  You will receive these from WestFax when requesting API credentials.  Additionally, you can configure the encoding to be what you prefer. The “RespEnc” variable can be JSON, JSON2, or XML. The “FaxIds1”, “FaxIds2”, and “FaxIds3” variables should be left alone. Their values will be set to responses from some API methods that are needed as inputs for other API methods.

#### Running the API Methods

After configuring the Environment variables, you should be able to start running API methods. In the left menu, there should be a folder labeled “WestFax.API” and have 23 items in it. Click on the first item called “Security_Ping” and then click the “Body” tab under the Post section. This is where the parameters that are being sent to the API are shown and can be changed. The “StringParams1” variable has a string value of “ping”. Once the send button in the upper right is clicked, the raw response from the API should show up and in the response should be a string “Pong – ping ”. This means that the API is working properly. Once you have a good idea of how the Postman tool works, work your way down the list of API calls to see how the workflow goes. 

Note: API methods with “Inbound” in their name will not work if you do not have an inbound Fax number on your product.

Note: It is possible that you have not received any inbound faxes on your account.  If you have not, then the inbound fax API methods will not work.  Send a fax to your inbound number and try them again once the fax has sent successfully.  Again -- you can use the “Fax_SendFax” API method itself to initiate this Fax.  You may have to wait a minute or 2 for the WestFax system to actually deliver the fax to your account.

Note: Certain API methods require resulting information from API methods run before them. For example, the “Fax_GetFaxDescriptionsUsingIds” API method requires the Ids in the response of the “Fax_GetFaxIdentifiers” API method as parameters. To make this easier to run, copy the response Ids and then go to the “Pre-request Script” tab next to the “Body” tab in the method that needs the ids as parameters and replace the ids in the JavaScript with the ones that were copied.

We recommend that you use the Postman tool with the SDK Demo since they mirror each other. We hope that the Postman collection along with the SDK Demo will get you underway with your integration quickly.  

####About WestFax
WestFax offers Enterprise [HIPAA Compliant Cloud Fax](https://westfax.com/hipaa-compliant-fax/) service through the WestFax online portal, our API and our mobile apps. We continue to innovate though Direct Message Protocol ready document capture, OCR and managed document workflow.


