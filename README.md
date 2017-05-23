# Paytm_Web_Sample_Kit_Java

Use below method of jar to generate checksum and verify checksum as per your JDK version

  1. generate checksum:  
    public String genrateCheckSum(String Key, TreeMap<String, String> paramap)
  2. generate checksum for Refund Request: 
    public String genrateRefundCheckSum(String Key, TreeMap<String, String> paramap)
  3. verify checksum: 
    public boolean verifycheckSum(String masterKey, TreeMap<String, String>  paramap,String responseCheckSumString)

# If you are on IBM websphare:

  1. generate checksum: 
    public String genrateCheckSumIBMJCE(String Key, TreeMap<String, String> paramap)
  2. generate checksum for Refund Request: 
    public String genrateRefundCheckSumIBMJCE(String Key, TreeMap<String, String> paramap)
  3. verify checksum: 
    public boolean verifycheckSumGAE(String masterKey, TreeMap<String, String>  paramap,String responseCheckSumString)

# If you are on Google App engine: 

  1. generate checksum:  
    public String genrateCheckSumGAE(String Key, TreeMap<String, String> paramap)
  2. generate checksum for Refund Request: 
    public String genrateRefundCheckSumGAE(String Key, TreeMap<String, String> paramap)
  3. verify checksum: 
    public boolean verifycheckSumIBMJCE(String masterKey, TreeMap<String, String>  paramap,String responseCheckSumString)
    
