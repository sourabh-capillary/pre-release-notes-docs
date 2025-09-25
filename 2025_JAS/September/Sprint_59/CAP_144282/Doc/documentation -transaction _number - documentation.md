**Link to doc** :https://docs.capillarytech.com/docs/manage-coupons\#revoke-coupons-with-returned-transactions

Revoke coupons with returned transactions

When a transaction is returned, the system automatically revokes any coupons issued against it. This prevents customers from misusing benefits tied to invalid purchases and maintains program integrity. The process is triggered by a return transaction event notification.

### **Key APIs used**

* [Get Customer Coupons V2](https://docs.capillarytech.com/reference/get-customer-coupons-basic#/)  
* [Revoke Coupon](https://docs.capillarytech.com/reference/revoke-coupon#/)

### **Workflow**

* A return transaction generates an event notification.  
* The Neo workflow captures the transaction ID from the event.  
* The workflow calls Get Customer Coupons V2 API to retrieve coupons linked to the transaction ID.  
* The workflow extracts the coupon ID.  
* The workflow calls the Revoke Coupon API to revoke the coupon.

Step 1: Capture the transaction ID

When a return transaction event is triggered, Neo captures the transaction ID from the payload. You will map this field in your Neo workflow configuration.

Step 2: Get Customer Coupons

Use the Get Customer Coupons V2 API to retrieve all coupons linked to the captured transaction ID.

Request

Sample Request

curl \--location 'https://{host}/v2/customers/coupons?transactionNumber=ABC123' \\  
  \--header 'Accept: application/json' \\  
  \--header 'Content-Type: application/json' \\

  \--header 'Authorization: Bearer \<token\>'

Response

Sample Response

{  
  "coupons": \[  
    {  
      "couponId": "HUHUHU123",  
      "status": "active",  
      "transactionNumber": "ABC123"  
    }  
  \]  
}

Step 3:Revoke Coupon

Use the couponId from Step 2 in the Revoke Coupon API. Request

Request sample

curl \--location 'https://{Host}/v2/coupons/revoke' \\  
  \--header 'Accept: application/json' \\  
  \--header 'Content-Type: application/json' \\  
  \--header 'Authorization: Bearer \<token\>' \\  
  \--data '{  
    "couponId": "HUHUHU123"

  }'

Response

Response sample

{  
  "couponId": "HUHUHU123",  
  "status": "revoked"

}

### **Configuration in Neo**

* Create a new workflow triggered by Return Transaction Event Notification.  
* Add a step to capture the transaction ID from the event.  
* Add a step to call Get Customer Coupons V2 with the transaction ID as a filter.  
* Parse the response to extract the couponId.  
* Add a final step to call Revoke Coupon API using the couponId.

