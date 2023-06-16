# Biller
This **Biller** category may be used for a variety of APIs, including : <br>
- 🚰 **PDAM** <br>
- ⚡ **PLN Prepaid**

**API Workflow** that is available for integration are “inquiry, payment, advice, and callback”.

1. Inquiry : Every time a payment occurs, **Service User** will make an inquiry to the **Service Provider** to get details of the payment/billing.
2. Payment : In this process **Service User** will pay the amount according to billing or price from the inquiry response.
3. Advice : Advice is used for checking the final status of transactions. Do this step if you get the condition below (do the advice process until getting the final status success/failed):
	- While payment can’t get any response (timeout, intermittent network, etc).
	- While payment gets a response with response code 02 (pending).
4. Callback : When the payment result is pending, **Service Provider** will notify **Service User** of the final status of the transaction.

![Use Case Diagram API List](https://drive.google.com/uc?id=1RvmHgAJCidFZC159m65naGvrxlpUXIJC "Use Case Diagram API List")
	<center>**Picture 1 : Use Case Diagram API List**</center>
	<br>

![Sequence Diagram API Workflow](https://drive.google.com/uc?id=14uHqKKBr21l_AkI_oQNAgcApAoDZANE7 "Sequence Diagram API Workflow")
	<center>**Picture 2 : Sequence Diagram API Workflow**</center>
	<br>