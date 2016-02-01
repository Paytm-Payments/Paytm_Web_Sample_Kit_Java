# Introduction
This is a Sample Kit for a webserver installation using Java.

# Mechanics of the Flow

 1. The folder *paytm_java* has a sample kit which can be deployed on a web server.
 2. It contains the three jsp files namely, paytm_java/WebContent/pgRedirect.jsp, paytm_java/WebContent/pgResponse.jsp and paytm_java/WebContent/TxnTest.jsp
 3. Open TxnTest.jsp in your browser. It will contain dummy data values.
 4. Submit the details.
 5. This will combine the input values and invoke the pgRedirect.jsp which in turn will take the control to the Payment page.
 6. Use the Login credentials given [here](https://paytm-wallet-sdk.readme.io/docs/on-boarding-guidelines) (within point *d*) to login and complete a test payment.
 7. Upon completion of the test payment, the control will pass to the Callback URL. As it is a sample app, this URL is configured as *localhost*. 
 **NOTE**: This value is configured in the pgRedirect.jsp. For Production it needs to be the URL of the production server's Callback.
 8. Based on the java version, you may choose the appropriate Checksum jar file from the provided Java Plugins. For the sample kit, the jar file being used is for Java 1.7 and its location is *paytm_java/WebContent/WEB-INF/lib/*.
