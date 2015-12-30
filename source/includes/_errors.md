# Errors

<aside class="notice">This error section is stored in a separate file in `includes/_errors.md`. Slate allows you to optionally separate out your docs into many files...just save them to the `includes` folder and add them to the top of your `index.md`'s frontmatter. Files are included in the order listed.</aside>

The Veritrans API uses the following status codes:


Status Code | Description
---------- | ------------
200	| __Credit Card:__. `Success`. Request is successful, and transaction is successful (authorize, capture, settlement, cancel, get order, approve challenge transactions), accepted by Veritrans and bank. <br><br> __Other payment methods:__ `Success`. Transaction is successful/settlement. |
201	|__Credit Card:__. `Challenge`. Transaction successfully sent to bank but the process has not been completed, need manual action from merchant to complete the transaction process. If the merchant does not perform any action until settlement time (H+1 16:00) Veritrans will cancel the transaction. <br><br> __Bank Transfer:__ `Pending`. Transaction successfully sent to bank but the process has not been completed by the customer. By default the transaction will expire within 24 hours. <br><br> __Cimb Clicks:__ `Pending`. Transaction successfully sent to bank but the process has not been completed by the customer. By default the transaction will expire within 2 hours. <br><br> __BRI ePay:__ `Pending`. Transaction successfully sent to bank but the process has not been completed by the customer. By default the transaction will expire within 2 hours. <br><br> __Klik BCA:__ `Pending`. Transaction successfully sent to bank but the process has not been completed by the customer. By default the transaction will expire within 2 hours. <br><br> __BCA Klikpay:__ `Pending`. Transaction successfully sent to bank but the process has not been completed by the customer. By default the transaction will expire within 2 hours. <br><br> __Mandiri Bill Payment:__ `Pending`. Transaction successfully sent to bank but the process has not been completed by the customer. By default the transaction will expire within 2 hours. <br><br> __XL Tunai:__ `Pending`. Transaction successfully sent to provider but the process has not been completed by the customer. By default the transaction will expire within 2 hours. <br><br> __Indomaret:__ `Pending`. Transaction successfully sent to provider but the process has not been completed by the customer. By default the transaction will expire within 2 hours. <br><br> __BBM Money:__ `Pending`. Transaction successfully sent to provider but the process has not been completed by the customer. By default the transaction will expire within 2 hours.|
202	| __Credit Card:__ `Denied`. Transaction has been processed but is denied by payment provider or Veritrans' fraud detection system. <br><br> __Other payment methods:__ `Denied`. Transaction has been processed but is denied by payment provider. |
300	| Move Permanently, current and all future requests should be directed to the new URL|
400	| Bad Request -- Your request sucks|
401	| Access denied due to unauthorized transaction, please check client key or server key|
402	| Merchant doesn't have access for this payment type|
403	| The requested resource is only capable of generating content not acceptable according to the accepting headers that sent in the request|
404	| The requested resource is not found|
405	| Http method is not allowed|
406	| Duplicate order ID. Order ID has already been utilized previously|
407	| Expired transaction|
408	| Merchant sent the wrong data type|
409	| Merchant has sent too many transactions for the same card number|
410	| Merchant account is deactivated. Please contact Veritrans support|
411	| Token id is missing, invalid, or timed out|
412	| Merchant cannot modify status of the transaction|
413	| The request cannot be processed due to malformed syntax in the request body|
500	| Internal Server Error|
501	| The feature has not finished yet, it will be available soon|
502	| Internal Server Error: Bank Connection Problem|
503	| Internal Server Error. We're temporarially offline for maintanance. Please try again later.|
504	| Internal Server Error: Fraud detection is unavailable|