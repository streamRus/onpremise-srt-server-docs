# REST API (Full Manual)

> Source PDF: [API_EN.pdf](../pdf/API_EN.pdf)

## Page 1

OnPREMISE API REST Introduction All OnPremise series software uses a REST API to deploy all its functionality and the JSON format to receive and deliver the data models it exchanges.

All calls and data models used by the API are self-documented via Swagger 2.0 by the same HTTP server that deploys the back-end. From the same local network of the device with the software installed, such

### documentation can be accessed from any browser using the URL

http:// local_ ip_ device /swagger . The Swagger interface not only documents each component, but can also be used to test those components. From the same web site you can download the doc.json file to be imported into Postman for detailed testing

by any front-end developer. API calls that are locked require the use of authentication for proper operation. 1


## Page 2

Authentication process Before we start using any authentication-protected API call, we have to get the apiKey, which we will use in

### each call, in the header of each request, like here

Authorization: apiKey To do this, we will first use the unprotected call in the auth section: POST /login. Using the api.Login model, we pass the user name and password that are stored at that time (defaults: admin/

admin). In this example, we receive as a response inside the session.APIKey model, the value of the apiKey SuGxqJY0XCzptuc3c1odevYqg8, which we will use in the locked calls, passing them in the header:

Authorization: SuGxqJY0XCzptuc3c1odevYqg8

### The generic response model is api.HTTPResponse with this composition

2


## Page 3

Let's see as an example of an authenticated call, the call in the network section GET /network. Which returns the following response in the body (metal.Network model) and in the headers:

Every session has a duration of 1440 seconds (24 minutes), which is updated in every new API call. If we are that time making no calls, that update will timeout, the session will expire automatically and we will need a

new apiKey, with the same process described above. We can also voluntarily logout by using the call DELETE /logout . The HTTP server is CORS-compliant, so you can create a front-end application that calls the full OnPremise

REST API from the outside. 3


## Page 4

Install your own panel on your device Apart from being able to use the API from external applications that call the device remotely, you can also create your own front-end panel with your own design and branding. In fact you can test it beforehand

### remotely, and if everything is ok, just upload it to the device as follows

1.- We compress in a zip file, the root of the front-end.

### 2.- We access the Upload Form of the device that is in the URL

http://ip_local_ device /upload?licid=licid_ d evice 4


## Page 5

Select the zip file that we created in step 1, and click Upload.

### If everything goes fine, a window like this one will be shown

3.- We can now load the new app again in our browser, refreshing the cache using Ctrl+F5 several times.. The original panel installed inside OnPremise software, delivers the most basic and generic functionalities in

the API, and has been created with Angular JS in typescript. If you are interested in creating your own panel and do not have front-end developer staff, you can contact us for quotation.

5
