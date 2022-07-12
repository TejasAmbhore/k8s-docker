
### Currency Exchange Service

If you ask it the value of 1 USD in INR, or 1 Australian Dollar in INR, the Currency Exchange Service answers 
- 1 USD is 60 INR
- 1 Australian Dollars is 50 INR. 

http://localhost:8000/currency-exchange/from/EUR/to/INR


### Currency Conversion

Currency Conversion Service is used to convert a bucket of currencies. If you want to find the value of 10 USD, Currency Conversion Service returns 600. 
- **STEP 1** : Currency Conversion Service calls the Currency Exchange Service for the value of 1 USD. It gets a response back saying 60.
- **STEP 2** : The Currency Conversion Service then multiplies 10 by 60, and returns 600 back. 

http://localhost:8100/currency-conversion/from/EUR/to/INR/quantity/10


#### How does Currency Conversion know the location of Currency Exchange?
- You don't want to HARDCODE
- Configure an Environment Variable - `CURRENCY_EXCHANGE_SERVICE_HOST`
- --env CURRENCY_EXCHANGE_SERVICE_HOST=http://currency-exchange
