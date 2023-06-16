# Topup
This **Toupup** category may be used for a variety of APIs, including : <br>
- 💳 **Flazz BCA**

**API Workflow** that is available for integration are “inquiry, payment, advice, and callback”.

1. Credential : The credential is used to generate a secure session for a user before initiating a transaction. Once the user's credentials are verified, the server generates a unique session ID.
2. Inquiry : Every time a payment occurs, **Service User** will make an inquiry to the **Service Provider** to get details of the payment/billing.
3. Payment : In this process **Service User** will pay the amount according to billing or price from the inquiry response.
4. Acknowledge : The Acknowledge API is a system that is used to store logs of successful transactions after the balance of the card updated.
5. Reversal : The Reversal API is a system that is used to reverse a credit transaction that has already been completed.
6. Advice : Advice is used for checking the final status of transactions and getting the payload for updating the card balance. Do this step if you get the condition below (do the advice process until getting the final status success/failed):
	- While payment can’t get any response (timeout, intermittent network, etc).
	- While payment gets a response with response code 02 (pending).

![Use Case Diagram API List](https://drive.google.com/uc?id=1tpgxVYGn07LgEDmYFrUhwkIrega66BYS "Use Case Diagram API List")
	<center>**Picture 1 : Use Case Diagram API List**</center>
	<br>

![Sequence Diagram API Workflow](https://drive.google.com/uc?id=1OnUee0gIJixN0PgPUnHHU1NUjBGsigHn "Sequence Diagram API Workflow")
	<center>**Picture 2 : Sequence Diagram API Workflow**</center>
	<br>