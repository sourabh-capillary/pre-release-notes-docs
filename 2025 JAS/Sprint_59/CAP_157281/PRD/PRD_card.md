## Use Case IV \- PII deletion handling

*As a loyalty program administrator setting up a card-based program or loyalty cards, I want to define handling for the card entity when a customer PII is deleted.*

This is once again a related use case to the card entity that we want to sort out. As of now, on PII deletion of customer data, the cards linked to the customer remain as is as we persist user ID after deletion. We want to incorporate automation that will do the following:

1. The administrator should be able to set a delinking policy for PII deleted accounts. Like the status automation above, each brand will have its own policy with respect to whether a card should remain with the deleted customer account.  
     
   Hence, we will have a configuration *CONF\_DELINK\_CARDS\_PII\_DELETION* to drive this \- if the configuration is enabled at a series level, on PII deletion, cards linked to the customer will be delinked from that customer. By default, we should enable this configuration for any new card series that will get created going forward. Also, if the configuration is enabled for an existing card series in an organization, we should honor it from the time it is enabled. 

2. Change the card status as per the expectations of the configurer at a card series level \- That means, on completion of PII deletion process and post de-linking as per above, the administrator should be able to define the status the cards linked to the customer should change to. This is a configuration that would be dependent on whether the *CONF\_DELINK\_CARDS\_PII\_DELETION* configuration is enabled.  
     
   For example, one brand might want to mark the status as NOT ISSUED while another might want to mark the card status as DELETED. Hence, we will keep this flexible \- the administrator will be able to, at a card series level, define the status/status label that a card linked to a PII deleted customer will change to. 

To summarize

- We will have a configuration \- at each card series level \- for automating delinking of cards associated with a customer whose PII is deleted. The delinking should trigger alongside the PII deletion process. The configuration should be enabled for all new orgs/series going forward.  
- Once the delinking is done, we should change the delinked card status as per the configuration set by the administrator. 

### Queries

* We should have a configuration which will allow clean up of card custom fields and extended fields when a card is delinked from a customer. We will look into this later.

