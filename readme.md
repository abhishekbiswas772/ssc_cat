## SandBox Keys
```
SANDBOX_API_KEY = "key_live_HuGvlFgGBPuqb72PhLRjC5RQy0Z6bDpS"
SANDBOX_API_SECRET = "secret_live_q4BREqHRU3GTr52cm5Oc6XfJb53JXPny"
```

## API-1
### Authenticate

For Getting Access Token

Request:-
```
end_point:- https://api.sandbox.co.in/authenticate
method:- POST
headers:- {
    "x-api-key" : "key_live_HuGvlFgGBPuqb72PhLRjC5RQy0Z6bDpS",
    "x-api-secret" : "secret_live_q4BREqHRU3GTr52cm5Oc6XfJb53JXPny",
    "x-api-version" : 1.0,
    "accept" : "application/json"
}
```


Response:- 
```
{
    "access_token": "<Access_Token>"
}
```


## API-2
### Authorize

API to refresh the JWT access token required to call Sandbox APIs

Request:-
```
end_point:- https://api.sandbox.co.in/authorize?request_token=<Access_Token>
method:- POST
headers:- {
    "accept": "application/json",
    "Authorization": <Access_Token>,
    "x-api-key": "key_live_HuGvlFgGBPuqb72PhLRjC5RQy0Z6bDpS",
    "x-api-version": "1.0"
}
```

Response:- 
```
{
  "access_token": "<Refresh_Token>"
}
```



## API 3
### API For Sending OTP to Registered Aadhaar 

Sandbox API to get OTP 

Request:-
```
end_point:- https://api.sandbox.co.in/kyc/aadhaar/okyc/otp
method:- POST
headers:- {
    "accept": "application/json",
    "Authorization": "<Access_Token>",
    "x-api-key": "key_live_HuGvlFgGBPuqb72PhLRjC5RQy0Z6bDpS",
    "x-api-version": "1.0",
    "content-type": "application/json"
}
payload / body:- { 
    "aadhaar_number": <Aadhaar Number 12 digit>
}
(Raw json format)
```

Response:-
```
{
    "code": 200,
    "data": {
        "ref_id": "7367353",
        "message": "OTP sent successfully"
    },
    "timestamp": 1700467483027,
    "transaction_id": "17192b65-886c-4d2e-ad29-2b0feeefea85"
}
```


## API 4 
### For Verifing OTP

Sandbox API to get verify OTP 

Request:-
```
end_point:- https://api.sandbox.co.in/kyc/aadhaar/okyc/otp/verify
method:- POST
headers:- {
    "accept": "application/json",
    "Authorization": "<Access_Token>",
    "x-api-key": "key_live_HuGvlFgGBPuqb72PhLRjC5RQy0Z6bDpS",
    "x-api-version": "1.0",
    "content-type": "application/json"
}
payload / body:- {
  "otp": {{otp}},
  "ref_id": {{ref_id}}
}
(Raw json format)
```
Response:-
```
{
  "code": 200,
  "data": {
    "ref_id": "7367353",
    "status": "VALID",
    "message": "Aadhaar Card Exists",
    "care_of": "",
    "dob": "16-02-1999",
    "email": "",
    "gender": "M",
    "name": "ABHISHEK BISWAS",
    "year_of_birth": "1999",
    "mobile_hash": "",
    "photo_link": "",
    "split_address": {
      "country": "India",
      "dist": "North 24 Parganas",
      "house": "",
      "landmark": "",
      "pincode": "",
      "po": "",
      "state": "West Bengal",
      "street": "",
      "subdist": "North 24 Paraganas",
      "vtc": ""
    }
  },
  "timestamp": 1700467748624,
  "transaction_id": "74497ea8-937b-48c3-ab09-fc909b3ac8cf"
}
```

