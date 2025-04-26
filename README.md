# Swiss Bitcoin Conference Kreuzlingen 2025 


## L402 Ablauf Beispiel

### GET Request 
Falls implementiert liefert der GET Request Infos zum Webservice.

```
curl --location --request GET 'https://sats4ai.com/api/l402/sms'
```


### POST Request 
Unautorisierter POST Request liefert Authorization Header welcher Lightning Invoice und Macaroon enthält. 

```
curl --verbose --location --request POST 'https://sats4ai.com/api/l402/sms' \
--header 'Content-Type: text/plain' \
--data-raw '{
    "phone_number": "+41796754690",
    "message": "I’m sure that in 20 years there will either be very large transaction volume or no volume. - Satoshi Nakamoto"
}'


```


### Autorisierter POST Request 
Um den Service effektiv zu nutzen muss ich die Invoice bezahlen und zusammen mit dem Macaroon im Header mitschicken.

```
curl --verbose --location --request POST 'https://sats4ai.com/api/l402/sms' \
--header 'Authorization: L402 <macaroon>:<preimage>' \
--header 'Content-Type: text/plain' \
--data-raw '{
    "phone_number": "+41796754690",
    "message": "I’m sure that in 20 years there will either be very large transaction volume or no volume. - Satoshi Nakamoto"
}'
```



Beispiel Request inkl. Macaroon und Invoice:

```
curl --verbose --location --request POST 'https://sats4ai.com/api/l402/sms' \
--header 'Authorization: L402 MDAyMWxvY2F0aW9uIDExMS8rNDE3OTY3NTQ2OTAvOTQKMDAxOGlkZW50aWZpZXIgaWQ1NTUxaWQKMDAyZnNpZ25hdHVyZSDARuVDYjUdGbAieejReJi9kYNsMmB1jf2f81hldx2akwo:741b0a227d6606f73131f73ff4532f071cc95523a1c2d2b45e4aa4a1bba00d38' \
--header 'Content-Type: text/plain' \
--data-raw '{
    "phone_number": "+41796754690",
    "message": "I’m sure that in 20 years there will either be very large transaction volume or no volume. - Satoshi Nakamoto"
}'
```


