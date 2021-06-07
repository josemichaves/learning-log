# SOAP API

![](../../.gitbook/assets/image%20%2824%29.png)

SOAP is the Simple Object Access Protocol, a messaging standard defined by the World Wide Web Consortium and its member editors. SOAP uses an XML data format to declare its request and response messages, relying on XML Schema and other technologies to enforce the structure of its payloads.

A standard request in XML from a SOAP API looks like this:

```markup
<?xml version="1.0"?>
<soap:Envelope xmlns:soap="http://www.w3.org/2003/05/soap-envelope">
  <soap:Header>
  </soap:Header>
  <soap:Body>
    <m:GetUser>
      <m:UserId>123</m:UserId>
    </m:GetUser>
  </soap:Body>
</soap:Envelope>
```

And a response look like this:

```markup
<?xml version="1.0"?>

<soap:Envelope
xmlns:soap="http://www.w3.org/2003/05/soap-envelope/"
soap:encodingStyle="http://www.w3.org/2003/05/soap-encoding">

<soap:Body>
  <m:GetUserResponse>
    <m:Username>Tony Stark</m:Username>
  </m:GetUserResponse>
</soap:Body>

</soap:Envelope>
```

We have the different tag that shows different categories of data

* Envelope: The `soap:Envelope` tag provides a mechanism to identify the XML as SOAP.
* Header: The `soap:Header` makes possible SOAP’s extensibility via SOAP Modules.
* Body:  The `soap:Body` contains the bulk of the SOAP message. Namespaces can be used to describe what data to expect within the body, but are not required. In practice, the name of the procedure, parameters, and data all come through the SOAP Body.
* Fault: The `soap:Body` tag for error messages when a SOAP API call is not able to complete. There are many possible causes for an error, including inaccurate SOAP formatting, a processing error on the server, and mismatched data type.

SOAP is still used as it's more secure than REST, if you're forced to use a rigid specification of how to send the data or if you need stateful operations. But if you don't need this REST is more modern, used, flexible and easy to use than SOAP.

