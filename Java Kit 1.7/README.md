# Usage of CheckSum Utility:  
 1. Add provided “paytm-checksum-1.1.jar” as a “Reference” in your project.
 2. Now Generate CheckSum API as well as Verify CheckSum API are available as follows:
    1. String CheckSumServiceHelper.genrateCheckSum(String merchantKey,TreeMap reqMap);
    2. boolean  CheckSumServiceHelper.verifycheckSum (String merchantkey, TreeMap   responseTreeMap, String responseChecksum);
 3. For Generating CheckSum, use following snippet code:
```sh
com.paytm.merchant.CheckSumServiceHelper checkSumServiceHelper = com.paytm.merchant.CheckSumServiceHelper.getCheckSumServiceHelper();
TreeMap<String,String> parameters = new TreeMap<String,String>();
String merchantKey = "xxxxxxxxxxxxxxxxx"; //Key provided by Paytm
parameters.put("MID", "xxxxxxxxxxxxxxxxxxxxxx"); // Merchant ID (MID) provided by Paytm
parameters.put("ORDER_ID", "nnnnnnnnn"); // Merchant’s order id
parameters.put("CUST_ID", "CUST001"); // Customer ID registered with merchant
parameters.put("TXN_AMOUNT", "1");
parameters.put("CHANNEL_ID", "WEB");
parameters.put("INDUSTRY_TYPE_ID", "Retail"); //Provided by Paytm
parameters.put("WEBSITE", "xxxxxxxxxxx"); //Provided by Paytm
//Note: Above mentioned parameters are not complete list of parameters. Please refer integration document for additional parameters which need to be passed.
String checkSum = CheckSumServiceHelper.genrateCheckSum(merchantKey, parameters);
```

4. For Verifying CheckSum, use following snippet code
```sh
com.paytm.merchant.CheckSumServiceHelper checkSumServiceHelper = com.paytm.merchant.CheckSumServiceHelper.getCheckSumServiceHelper();
TreeMap<String,String> parameters = new TreeMap<String,String>();
String paytmChecksum = "xxxxxxxxxxxx"; // Sent by Paytm pg
boolean isValidChecksum = false;
paytmChecksum = request.getParameter("CHECKSUMHASH");
String merchantKey = "xxxxxxxxxxxxxxxxx"; //Key provided by Paytm
parameters.put("MID", "xxxxxxxxxxxxxxxxxxxxxx"); // Merchant ID (MID) sent by Paytm pg
parameters.put("TXNID", ""); // Transaction id sent by Paytm pg
parameters.put("ORDER_ID", "nnnnnnnnn"); // Merchant’s order id
parameters.put("BANKTXNID", "xxxxxxxxxxxx");  // Bank TXN id sent by Paytm pg
parameters.put("TXN_AMOUNT", "1");
parameters.put("STATUS", " TXN_FAILURE"); //sent by Paytm pg
parameters.put("RESPCODE", "xxxxxxxxxxx"); //sent by Paytm pg
//Note: Above mentioned parameters are not the complete list of parameters. Please refer integration document for additional parameters which need to be passed.
isValidChecksum = CheckSumServiceHelper.verifycheckSum (merchantkey, parameters, paytmChecksum);
```

# Configurations at merchant server: 
 1. Need to copy local_policy.jar and US_export_policy.jar files in JRE folder "/jre/lib/security/"
 2. JRE6: Extract "jce_policy-6.zip" file & copy above files in "/jre/lib/security/"
 3. JRE7: Extract "UnlimitedJCEPolicyJDK7.zip" file & copy above files in "/jre/lib/security/"
