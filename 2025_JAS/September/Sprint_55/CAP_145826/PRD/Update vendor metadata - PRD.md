### **Use case 2 : Ability to update the vendor metadata**

**Product requirement:**

1. Allow the user to update the vendor metadata  
   1. Name : Remove the uniqueness check on name  
   2. Description  
   3. Rank  
   4. Images  
   5. Videos  
   6. Status: enabled/disabled  
   7. Code : uniqueness check on this. It should not be case-sensitive.  
   8. Key-value pairs  
      1. Can be added  
      2. Can be updated  
      3. Can be removed

{  
           "id": 71,  
           "name": "testvendor1",  
           "brandId": 1,  
           "enabled": **true**,  
           "vendorTypes": **null**,  
           "vendorDetails": {},  
           "type": "REWARDS",  
           "rank": **null**,  
           "code": "abc730ea-bd1e-4511-ba5f-3852b19567c0",  
           "description": **null**,  
           "images": \[\],  
           "videos": \[\],  
           "lastUpdatedOn": 1741077648000,  
           "encryptionRequired": **false**  
       }

