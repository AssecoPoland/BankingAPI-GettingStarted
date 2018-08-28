## Welcome to the Retail Banking API

Our API allow easy and secure access to bank accounts, customer data, many payment methods, and much more.

Our APIs are RESTful. We use JSON format and OAuth authorization based on JSON Web Token.

This API is a sandbox version, and its purpose is to make developers familiar with the upcoming API production release. Moreover, it allows the developers to experiment and build applications which use the API before its official release. See sandbox for more information regarding the sandbox and what it is.

The purpose of this documentation is to give an overview of all the API which are included in API sandbox. There is separate documentation for each API which includes the full API reference of the particular API and any specific information which is not presented in this overview.

### Getting Started

To start working with our API You need information about:
- jwtToken - authorization token which is provided by our organization
```
Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJhdWQiOlsicmViLWN1c3RvbWVyLXNlcnZpY2UiXSwidXNlcl9uYW1lIjoiTUIxQk1PNlIiLCJpZGVudGl0eSI6eyJvcmdfdW5pdCI6Im91PTk0NixvPVNHQi1CQU5LLGRjPUFDUCxkYz11ZmUsZGM9Y29tIiwicGVyc29uX2lkIjoiMzI4MDM4Iiwicm9sZSI6IkNVU1RPTUVSIiwiYWNjZXNzX3Byb2ZpbGVfaWQiOiIyMDA3In0sInNjb3BlIjpbIndyaXRlIiwicmVhZCJdLCJpc3MiOiJpc3N1ZXIiLCJqdGkiOiJlYmY0ZGZmYS00ZWU2LTQ4NGUtODdiMy1hYzc5MDk3ZWRmZjUiLCJhdXRob3JpdGllcyI6WyJST0xFX1VTRVIiXX0.W3ZMfIHLu401I3CKG0lv0Om3xPoZqeVn2DdJQEzPtyQ
```
- apiAddress - address of Your sanbox
```
https://cbp-api.asseco.pl/banking-service
```

- customerId - internal customer's identificator inside of bank
```
328038
```

- accessProfileId - internal customer's profile identificator inside of bank
```
2007
```

Below is a simple curl GET request to our API:
Before use please fill required parameters, jwtToken, apiAddress, customerId.

``` 
curl -k -X GET --header "Accept: application/json" --header "Authorization: jwtToken" "https://apiAddress/api/user/get/user_personal_details.json?customerId=customerId"
```

### Security issue

Production security flow based on OAuth2 flow and it's describe below:

     ----------------------Production--------------------------
     +--------+                               +---------------+
     |        |--(A)- Authorization Request ->|   Resource    |
     |        |                               |     Owner     |
     |        |<-(B)-- Authorization Grant ---|               |
     |        |                               +---------------+
     |        |
     |        |                               +---------------+
     |        |--(C)-- Authorization Grant -->| Authorization |
     | Client |                               |     Server    |
     |        |<-(D)----- Access Token -------|               |
     |        |                               +---------------+
     |        |
     ------------------------Sandbox---------------------------
     |        |                               +---------------+
     |        |--(E)----- Access Token ------>|    Resource   |
     |        |                               |     Server    |
     |        |<-(F)--- Protected Resource ---|               |
     +--------+                               +---------------+

In sandbox we provide You ready to use JWT token witch will not expire.

### Bussiness domain

#### /user
This resource describe personal information about bank's customers. User is in relation with below finance resources.

#### /account
This resource describe a basic banking product. It's finance registry closely related to bank customer. Main property of this resource is a finance balance.

#### /payments
This resource is created after the bank's customer decided to make some finance movement eg. money transfer to internal or external account. Every payment has their amount, currency and status which decide about payment's state. Not every payments has a finance effect cause rejection, limitations or user cancellation.

#### /transaction
This resource is created after the bank's customers do some payments and this payments was booked in Core Banking System.
Transaction is connected with payments from which it was created.

#### /credit
This resource reflects customer's financial liabilities towards the bank.

#### /deposit
This resource is connected with customers savings.

#### /card
This resource reflects a customers payment card. Every card is connected to customer account. Also debit card is supported in this area.

#### /card_transaction
This resource contains all information about card finanse operations eg. obtaining cash from an ATM, internet payments or shopping transactions.

### Tools

To integrate with our RESTful API You can use Your favourite tool. We suggest: 
[PostMan](https://www.getpostman.com)
[SoapUI](https://www.soapui.org) or symply 
[Curl](https://curl.haxx.se)
