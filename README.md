## Welcome to the Retail Banking API

Our API allow easy and secure access to bank accounts, customer data, many payment methods, and much more.

Our APIs are RESTful. We use JSON format and OAuth authorization based on JSON Web Token.

This API is a sandbox version, and its purpose is to make developers familiar with the upcoming API production release. Moreover, it allows the developers to experiment and build applications which use the API before its official release. See sandbox for more information regarding the sandbox and what it is.

The purpose of this documentation is to give an overview of all the API which are included in API sandbox. There is separate documentation for each API which includes the full API reference of the particular API and any specific information which is not presented in this overview.

### Getting Started



### Bussiness domain

#### /user
This resource describe personal information about bank's customers. User is in relation with below finance resources.

#### /account
This resource describe a basic banking product. It's finance registry closely related to bank customer. Main property of this resource is a finance balance.

#### /payments
This resource is created after the bank's customer decided to make some finance movement eg. money transfer to internal or external account. Every payment has their amount, currency and status which decide about payment's state. Not every payments has a finance effect cause rejection, limitations or user cancellation.

#### /transaction
information about transactions on user account

#### /credit
user credit list

#### /deposit
user deposit list

#### /card
This resource reflects a customers payment card. Every card is connected to customer account. Also debit card is supported in this area.

#### /card_transaction
This resource contains all information about card finanse operations eg. obtaining cash from an ATM, internet payments or shopping transactions

### Tools

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/bukalaACP/hackathon-2018/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with API? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
