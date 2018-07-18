.. _direct_api:

Balancing 2.0
####################

.. contents:: 
    :local: 

.. role:: ex

.. role:: code

General Information
----------------------------

|The new balancing allows distributing traffic between payment gates flexibly depending on the defined criteria and customer's transaction data.
|Traffic can be routed to a specific group of gates/processors and distributed between them in accordance with the specified balancing.
|The new balancing is configured on the system :ex:"Project" level in the :ex:"Balancing beta" tab.

|To start with the configuration, click :ex:"Configure".

 .. figure:: ../_static/pic1.png
       :scale: 100 %
       :align: center
       :alt: pic1 balancing 2.0

|A menu with an option to select one of several :ex:"routing types" will appear:

 .. figure:: ../_static/pic2balancing.png
       :scale: 100 %
       :align: center
       :alt: pic2 balancing 2.0


|Routing block will be formed by selecting one of them.
|The :ex:"by Source Card Type" routing is taken as an example:

 .. figure:: ../_static/pic3balancing.png
       :scale: 100 %
       :align: center
       :alt: pic3 balancing 2.0

|Its name and number are at the top of this block. The button for turning the block on and off is located to the left of the number (by default all the blocks are turned on). 
|The gear for the further setting of the block is located to the right of its name: it’s possible to “Remove routing” or :ex:“Add criteria”.
|Below the :ex:"routing type" name there is a "Criterion" named :ex:"OTHERS" - this is the default Criterion, that will be applied if the transaction does not match the parameters to the other created criteria (for "by Customer Loyalty" routing this criterion is not available).

|Click the settings gear of the Routing block and select :ex:"Add criteria"; depending on the previously selected Routing, the available criteria will differ.

 .. figure:: ../_static/pic4balancing.png
       :scale: 100 %
       :align: center
       :alt: pic4 balancing 2.0

|Select an appropriate one and add it (the criteria can be added either individually or in a group). Click the gear to the right of the Criterion name, and select a menu option:

|:ex:"Remove criteria", :ex:"Change criteria", :ex:"Add routing", :ex:"Add gates".

|If this criterion is enough, then you have to select the :ex:"Add gates" option and add one of the balancing types with the payment gate. 
|The :ex:"Balance by coefficient on Tx Amount" is taken as an example:

 .. figure:: ../_static/pic5balancing.png
       :scale: 100 %
       :align: center
       :alt: pic5 balancing 2.0

|Select the balancing type to make it available on the right side of the first block.

 .. figure:: ../_static/pic6balancing.png
       :scale: 100 %
       :align: center
       :alt: pic6 balancing 2.0

|Blocks are connected by arrows to improve the visual presentation. An arrow is directed from a certain criterion to the block created from it. 
|If the transaction parameters match the specified criterion, it is forwarded further along the arrow. 
|In the left top corner of new block, there is a block switch button, the block number, the balancing type (block name) and the gear for further configuration. 
|Click the gear to display the options: :ex:"Remove" the block, :ex:"Add gate", :ex:"Add group" of gates. When :ex:"Add gate" option is selected, several active fields will appear below from left to right:

 .. figure:: ../_static/pic7balancing.png
       :scale: 100 %
       :align: center
       :alt: pic7 balancing 2.0

     |1.	The probability percentage. This percentage determines how likely the transaction is to go to this gate. This field exists only for the types of balancing with a coefficient.
     |2.	The payment gate. In this field you can select the required gate.
     |3.	Three empty fields responsible for rate plans (tariffs) redistribution (see below).

|After selecting the parameters, click the gear with a check mark on the right to confirm the selection. If the transaction meets the created route conditions, it will be forwarded to the balancing block with this payment gate.
|For more routing criteria, click the gear of the required criterion and select "Add routing", then create the subsequent transaction path from it. New block appears to the right of the selected criterion with a new number and routing type name.

|The "by Source Card BIN" routing type is taken as an example:

 .. figure:: ../_static/pic8balancing.png
       :scale: 100 %
       :align: center
       :alt: pic8 balancing 2.0

|There is already an "OTHERS" default criterion below. As in the first case, click the gear and select "Add criteria" to add the appropriate criterion. 
|Depending on the required routing strategy and the traffic separation level, go on building the routes or finish the route by adding one of the balancing types and clicking "Add gates" to add the payment gate.
|After the New balancing configuration is set, enable it by going to the "Project" menu, clicking the "Edit" button and selecting the "Use new balancing" check box at the bottom of the page. 
|To confirm the selection, click "Update". 

 .. figure:: ../_static/pic9balancing.png
       :scale: 100 %
       :align: center
       :alt: pic9 balancing 2.0

|Now, the New balancing is applied and all the traffic will go through it.


Routing types
----------------------------

|Several "routing types" are used in the New balancing to configure the transaction routes more flexibly.

|:code:`Routing types` is a filter which allows to specify the traffic separation. Depending on the selected routing type, the transaction flow will be checked in relation to its parameters. 

|In the New balancing such routing types are represented as follows:

    |1)  The :code:`by Source Card Type` allows to sort transactions by the sender's card type. Select the appropriate payment methods of the sender and build a further route based on them.

     .. figure:: ../_static/pic10balancing.png
       :scale: 100 %
       :align: center
       :alt: pic10 balancing 2.0

    |2)	The :code:`by Source Card BIN` allows you to sort transactions by the sender's card BIN value. Select the needed BIN values of the sender and build a further route based on them.

     .. figure:: ../_static/pic11balancing.png
       :scale: 100 %
       :align: center
       :alt: pic11 balancing 2.0

    |3)	The :code:`by Source Card Bank` allows you to sort transactions by the sender's Issuer Bank name. Select the needed names of sender’s Issuer Banks and build a further route based on them.  

     .. figure:: ../_static/pic12balancing.png
       :scale: 100 %
       :align: center
       :alt: pic12 balancing 2.0

    |4)	The :code:`by Source Card Country` allows you to sort transactions by the sender's card Country. Select the needed countries of the sender and build a further route based on them.

     .. figure:: ../_static/pic13balancing.png
       :scale: 100 %
       :align: center
       :alt: pic13 balancing 2.0

    |5)	The :code:`by Destination Card Type` allows you to sort transactions by the receiver's card type. Select the needed card types of the receiver and build a further route based on them. 

     .. figure:: ../_static/pic14balancing.png
       :scale: 100 %
       :align: center
       :alt: pic14 balancing 2.0

    |6)	The :code:`by Destination Card BIN` allows you to sort transactions by the receiver’s card BIN value. Select the needed BIN values of the receiver and build a further route based on them.

     .. figure:: ../_static/pic15balancing.png
       :scale: 100 %
       :align: center
       :alt: pic15 balancing 2.0

    |7)	The :code:`by Destination Card Bank` allows you to sort transactions by the receiver’s Issuer Bank name. Select the needed Issuer Bank names of the receiver and build a further route based on them.
    
     .. figure:: ../_static/pic16balancing.png
       :scale: 100 %
       :align: center
       :alt: pic16 balancing 2.0

    |8)	The :code:`by Destination Card Country` allows you to sort transactions by the receiver’s card country. Select the required card countries of the receiver and build a further route based on them.

     .. figure:: ../_static/pic17balancing.png
       :scale: 100 %
       :align: center
       :alt: pic17 balancing 2.0

    |9)	The :code:`by Customer IP Country` allows you to sort transactions by the IP address of the customer's country. Select the countries, the IPs of which will be checked and build a further route based on them.

     .. figure:: ../_static/pic18balancing.png
       :scale: 100 %
       :align: center
       :alt: pic18 balancing 2.0

    |10) The :code:`by Customer IP Range` – allows you to sort transactions which IP address values are within the specified range. Specify the appropriate IP range and build the further route from it. Both IPv4 and IPv6 are accepted.

     .. figure:: ../_static/pic19balancing.png
       :scale: 100 %
       :align: center
       :alt: pic19 balancing 2.0

    |11) :code:`by Customer Billing Country` allows you to sort transactions by the country from the customer’s billing address. Select the needed countries and build a further route based on them.

     .. figure:: ../_static/pic20balancing.png
       :scale: 100 %
       :align: center
       :alt: pic20 balancing 2.0

    |12) :code:`by Customer Loyalty` allows you to sort transactions by the Customer loyalty type ("NEW" or "RETURNING"). 
    |“RETURNING” condition checks if the customer’s card is in white list or the e-mail is in anti-black list. All other transactions are considered as "NEW".  
    |Select the loyalty types and build a further route based on them.

     .. figure:: ../_static/pic21balancing.png
       :scale: 100 %
       :align: center
       :alt: pic21 balancing 2.0

    |13) :code:`by Transaction Amount` allows you to sort transactions by their amounts. Transactions, which amounts match the specified range, will pass through this routing criterion. 

     .. figure:: ../_static/pic22balancing.png
       :scale: 100 %
       :align: center
       :alt: pic22 balancing 2.0

    |14) :code:`by Transaction Type` allows you to sort transactions by their type. Select the needed transaction types and build a further route based on them.

     .. figure:: ../_static/pic23balancing.png
       :scale: 100 %
       :align: center
       :alt: pic23 balancing 2.0

    |15) :code:`by Transfer Direction` allows you to sort transfer transactions by card types or Issuer banks of sender and receiver. Select the needed parameters and build a further route based on them.

     .. figure:: ../_static/pic24balancing.png
       :scale: 100 %
       :align: center
       :alt: pic24 balancing 2.0

    |Gates can be specified directly on the endpoint. However, they will be 
    subject to the routing strategy.
   

Balancing types
----------------------------

|:code:`Balancing type` is a feature which allows to distribute transactions between payment gates in accordance with the configured parameters.

|The following balancing types are presented in the system:

|Balancing:

    |1):code:`Balance by coefficient on Tx Amount` allows to sort transactions by the gates depending on the amount and the specified probability percentage.

     .. figure:: ../_static/pic25balancing.png
       :scale: 100 %
       :align: center
       :alt: pic25 balancing 2.0

    |For example, 3 gates have 20%, 30% and 50% coefficients set for them. 
    |In this case, 50% of the first several processed transactions will be forwarded to the gate with the probability of 50%, then the traffic will try to reach the distribution of the amount between the gates in accordance with the specified percentages. 
    |If the processed amount on a gate exceeds the amounts on the other gates, the transactions will not be forwarded to the gate with the exceeding amount until the amounts on all the gates become equal to the percentages set for the gates. 

    |2):code:`Balance by coefficient on Tx Count` allows you to sort transactions by gates depending on their quantity and the specified probability percentage.

     .. figure:: ../_static/pic26balancing.png
       :scale: 100 %
       :align: center
       :alt: pic26 balancing 2.0

    |For example, 3 gates have 20%, 30% and 50% coefficients set for them. In this case, 50% of the processed transactions will be forwarded to the gate with the probability of 50%. 
    |The transaction amounts are not considered, only their quantity is.   

    |3):code:`Balance equally on Tx Amount` allows to sort transactions by gates depending on the amount with equal probability percentage.

     .. figure:: ../_static/pic27balancing.png
       :scale: 100 %
       :align: center
       :alt: pic27 balancing 2.0

    |If there are e.g. 4 gates, "Balance equally on Tx Amount" will set an equal probability percentage of 25% for each gate. The first several transactions can be forwarded to any of them as the percentages are equal, then the traffic will try to reach the equal distribution of the amount between the gates.
    |If the processed amount on a gate exceeds the amounts on the other gates, the transactions will not be forwarded to the gate with the exceeding amount until the amounts on all the gates become equal.

    |4):code:`Balance equally on Tx Count` allows to sort transactions by gates depending on the quantity with equal probability percentage.

     .. figure:: ../_static/pic28balancing.png
       :scale: 100 %
       :align: center
       :alt: pic28 balancing 2.0

    |If there are e.g. 4 gates, "Balance equally on Tx Count" will set an equal probability percentage of 25% for each gate. 
    |The first several transactions can be forwarded to any of them as the percentages are equal, then the traffic will try to reach the equal distribution between the gates based on the quantity of transactions.   

|Chain:

    |1):code:`Chain by Sequence` allows to sort transactions using the chain principle.

     .. figure:: ../_static/pic29balancing.png
       :scale: 100 %
       :align: center
       :alt: pic29 balancing 2.0

    |Transactions will be processed by gates only in a priority order. 
    |If for some reason the first gate in the chain was not able to process the transaction, it moves further along the chain until one of the subsequent gates in chain processes it. 
    |The gate priority can be changed in "Chain by Sequence" using drag'n'drop.

|Chain balancing:

    |1):code:`Chain by Coefficient on Tx Count` allows to sort transactions by gates using the specified probability percentage and the chain principle. If the incoming transaction is going to be filtered or exceed the limits on some gates, the balancing algorithm excludes these gates and then it forms the chain with the remaining ones according to their coefficients.

     .. figure:: ../_static/pic30balancing.png
       :scale: 100 %
       :align: center
       :alt: pic30 balancing 2.0

    |For example, 3 gates have 20%, 30% and 50% coefficients set for them. In this case, the gate with 50% coefficient has the 50% probability of becoming the first gate in the formed chain. 
    |If for some reason the first gate in chain was unable to process the transaction, it goes to the next gate in chain. If the second gate was not able to process the transaction as well, it moves on until one of the subsequent gates in chain processes it. 
    |The traffic will try to reach the distribution between the gates according to their coefficients based on the quantity of transactions.

    |2):code:`Chain by Equivalently on Tx Count` allows to sort transactions by gates using the chain principle and an equal probability percentage. If the incoming transaction is going to be filtered or exceed the limits on some gates, the balancing algorithm excludes these gates and then it forms the chain with the remaining ones based on equal probability percentage.

     .. figure:: ../_static/pic31balancing.png
       :scale: 100 %
       :align: center
       :alt: pic31 balancing 2.0

    |If there are e.g. 4 gates, "Chain by equivalently on Tx Count" will set an equal probability percentage of 25% for each gate. 
    |In this case, each gate has the 25% probability of becoming the first gate in the formed chain. 
    |If for some reason the first gate in chain was unable to process the transaction, it goes to the next gate in chain. 
    |If the second gate was not able to process the transaction as well, it moves on until one of the subsequent gates in chain processes it. 
    |The traffic will try to reach the equal distribution between the gates based on the quantity of transactions.   

|First in Sequence:

    |1):code:`First in Sequence` allows you to sort transactions by choosing the first appropriate gate for them. 

     .. figure:: ../_static/pic32balancing.png
       :scale: 100 %
       :align: center
       :alt: pic32 balancing 2.0   

    |If the incoming transaction is going to be filtered or exceed the limits on certain gates, the “First in Sequence” algorithm excludes these gates and then it sends the transaction to the highest gate of the remaining ones. 
    |The gate priority can be changed by dragging it up and down.

Chain strategy details
----------------------------

|:code:`Chain strategy details` allows to select which Declines (negative processing results) will continue or stop the chain. 

|If the configured routing has such balancing types as: Chain by Sequence, Chain by Equivalently on Tx Count, Chain by Coefficient on Tx Count, it’s possible to go to the "Chain 
|Strategy Details" tab on the gate level and select the criteria to continue or stop the chain.

 .. figure:: ../_static/pic33balancing.png
       :scale: 100 %
       :align: center
       :alt: pic33 balancing 2.0

|The number and name of the gate is at the top of the page. 
|The active line "Continue the chain" is located below and the choice of criteria is to the right of it. 
"Independently of the decline reason" is selected by default.

|Two active columns – "Unavailable" and "Available" – are located below. 
|The reasons for decline are located in the "Unavailable" field. 
|The chain can continue:

    |1) Independently of the decline reason
    |2) Only for the selected decline reasons
    |3) For any decline reason except the selected ones

|"independently of the decline reason" - the chain will continue regardless of the received decline codes.

|“Only for the selected decline reasons” - the chain will continue only for the specified decline reasons. Select the reasons from the "Unavailable" column with the check boxes next to them, and add them to the "Available" column by clicking the "Add" button. Remove the unwanted reasons by selecting them with the check boxes and clicking the "Remove" button. 
|Confirm the parameters with the "Save" button. 
|“For any decline reason except the selected ones” - the chain will continue for all reasons, EXCEPT for the specified ones. Select the reasons from the "Unavailable" column with the check boxes next to them, and add them to the "Available" column by clicking the "Add" button. 
|Remove the unwanted reasons by selecting them with the check boxes and clicking the "Remove" button. Confirm the parameters with the "Save" button.

Tariffs
----------------------------

|:code:`Tariff` is a system of payment fees for all stakeholders’ services.

|The system supports such stakeholders as:

|:ex:`Merchant`, :ex:`Reseller`, :ex:`Manager`, :ex:`Dealer`, :ex:`Bank`.

|In the current model, the fees are incrementally increasing, from the Bank to the Merchant. 
|The following rate plan will count the value of the previous one. Thus, the higher the participant’s level is, the greater his total fee is in the system. The Bank and Dealer rate plans can be set on the gate level. Manager, Reseller, and Merchant rate plans can be set on the project level, with the option to override them on the endpoint level. 
|The presence of some participants in the payment rates model is optional.

|In new balancing the tariffs can be redefined directly on the gates configuration in balancing blocks. 
|These tariff settings override the ones on the gate, project or endpoint level.

 .. figure:: ../_static/pic34balancing.png
       :scale: 100 %
       :align: center
       :alt: pic34 balancing 2.0

|There are 3 active fields to the right of the gate’s name, which are responsible for redefining rate plans for Manager, Reseller and Merchant, from left to right respectively. 
|All rate plans can be selected from the dropdown list of already created ones.       

Limits and Filters
----------------------------

|:code:`Limits and filters` are the configurable sets of rules which allow to restrict the traffic by certain criteria directly on the gate.

|:ex:`Filters`, which are applied in the new balancing, may be configured on the gate level. To switch them on, go to the required gate and click on the "Filters" tab

 .. figure:: ../_static/pic35balancing.png
       :scale: 100 %
       :align: center
       :alt: pic35 balancing 2.0

|There are such filters as:

    |1):code:`Check hourly limit` for the customer’s card. If the amount of transactions or their quantity exceeds the parameter values within the past 24 hours, the transactions will be filtered.

    |2):code:`Check weekly limit` for the customer’s card. If the amount of transactions or their quantity exceeds the parameters values within the past week, this filter rejects the transaction.

    |3):code:`Check monthly limit` for the customer’s card. If the amount of transactions or their quantity exceeds the parameters values within the past month, this filter rejects the transaction.

    |4):code:`Check destination hourly limit` for the receiver’s card. If the amount of transactions or their quantity exceeds the parameters values within the past 24 hours to one destination, this filter rejects the transaction.

    |5):code:`Check destination weekly limit` for the receiver’s card. If the amount of transactions or their quantity exceeds the parameters values within the past week to one destination, this filter rejects the transaction.

    |6):code:`Check destination monthly limit` for the receiver’s card. If the amount of transactions or their quantity exceeds the parameters values within the past month to one destination, this filter rejects the transaction.

    |7):code:`The Check e-mail hourly limit` filter rejects the transaction if the amount of transactions or their quantity to one e-mail address exceeds the parameters values within the past 24 hours.

    |8):code:`The Check e-mail weekly limit` filter rejects the transaction if the amount of transactions or their quantity to one e-mail address exceeds the parameters values within the past week.

    |9):code:`The Check e-mail monthly limit` filter rejects the transaction if the amount of transactions or their quantity to one e-mail address exceeds the parameters values within the past month.

    |10):code:`The Deny BIN country` filter rejects the transaction if the selected country BIN is included in the parameters.

    |11):code:`The Deny IP country` filter rejects the transaction if the selected country IP is included in the parameters.

    |12):code:`The Deny billing country` filter rejects the transaction if the Customer country of residence is included in the parameters. 

|To switch the required filter on, click the lamp symbol to the left of it. The filter setting will be available after the filter is switched on:

 .. figure:: ../_static/pic36balancing.png
       :scale: 100 %
       :align: center
       :alt: pic36 balancing 2.0    

|The following parameters will be available in the filters configurations of the "Check Limit" type: 

    |1)	The :code:`Allowable transaction amount` parameter specifies amount limits.

    |2):code:`For all gates with the same descriptor` – the filter will be extended to all the gates with the same descriptor. Specify the value "Y" (Yes) instead of "N" (No) to enable.

    |3)	The :code:`Allowable number of transactions` parameter specifies the transactions quantity limits. 


|The choice of "Country Identifier" will be available in the "Deny" filter configurations. 

|Each country is assigned its own numerical identifier. The required country can be chosen from the list. 

|:ex:`Limits`, which are applied in the new balancing, may be configured on the gate level. To switch them on, go to the required gate and click the "Limits" tab

 .. figure:: ../_static/pic37balancing.png
       :scale: 100 %
       :align: center
       :alt: pic37 balancing 2.0

|The currency of this gate is represented on the top of the opened page. Below are the payment systems supported by the processor connected to this gate. 

|The limits can be configured for all the payment systems or selectively, but the systems that are not planned to be limited have to be disabled. 
|To disable the traffic limitation by the payment system, click the "on" button to the left of its name (all the payment systems are enabled by default).

|Click on the "Edit" button at the top of the page to start the configuration. Only the enabled payment systems can be configured.  

|The following parameters are available: 

    |1):ex:`Sale`, :ex:`Auth`, :ex:`Transfer` row sets the limit for these operations on the given payment system. 

    |2):ex:`Chargeback` row sets the chargeback limit on the given payment system.

    |3):ex:`Fraud` row sets the fraud limit on the given payment system. 

 .. figure:: ../_static/pic38balancing.png
       :scale: 100 %
       :align: center
       :alt: pic38 balancing 2.0

|:ex:`Limits on the "Chargeback" and "Fraud" types of transactions are used for notifications and are displayed in the reports; they can not really limit such operations.`

|Click the "Save" button to save the parameters. 
|Click the "Revert" button to return to the previously specified settings. 









