# Authentication

## Signup

This API is used for the Signup with HonestContract application with some information.

```shell
 curl -X POST \
 http://baseurl/api/signup \
-H 'accept: application/json' \
-H 'cache-control: no-cache' \
-H 'content-type: application/json' \
-d '{
{
	"user":{
		"fname": "vikram",
		"email":"vikmar@gmail.com",
		"password":"abers56"
		"password":"******"
}
}'
```

> The above command returns JSON structured like this:

```json
{
	"user": {
		"id": 57,
		"fname": "vikram",
		"lname": null,
		"company_name": null,
		"company_title": null,
		"street": null,
		"unit": null,
		"street_name": null,
		"city": null,
		"state": null,
		"country": null,
		"pin": null,
		"email": "vikamsharma@gmail.com",
		"phone": null,
		"fax": null,
		"created_at": "2017-09-21 11:32:55",
		"updated_at": "2017-09-21 11:32:55"
	},
	"access_token": "ABCABCABC",
    "refresh_token": "DEFDEFDEF"
}
```



```json
{
  "error": [
    "Please enter the correct email address."
  ]
}
```



### HTTP Request

`POST http://baseurl/api/signup`


Parameter | Type    | Description | Required
--------- | ------- | ----------- | -----------
fname     | string   | Name of the user | true
email     | string  | Email address of the user | true
password  |  string | Password of the user | true


<aside class="success">Status code :200 OK </aside>
<aside class="warning">Error code : 422 Unprocessable Entity</aside>

## Sigin 

This API is used for the login with email and password.

```shell
curl -X POST \
http://baseurl/api/signin \
-H 'accept: application/json' \
-H 'cache-control: no-cache' \
-H 'content-type: application/json' \
-d '{
{
	"user":{
		"email":"vikmar@gmail.com",
		"password":"abers56"
	}
}
}
'

 ```


> The above command returns JSON structured like this:

```json
{
	"user": {
		"id": 57,
		"fname": "vikram",
		"lname": null,
		"company_name": null,
		"company_title": null,
		"street": null,
		"unit": null,
		"street_name": null,
		"city": null,
		"state": null,
		"country": null,
		"pin": null,
		"email": "vikmar@gmail.com",
		"phone": null,
		"fax": null,
		"created_at": "2017-09-21 11:32:55",
		"updated_at": "2017-09-21 11:32:55"
	},
	"access_token": "ABCABCABC",
    "refresh_token": "DEFDEFDEF"
}
```

```json
{
  "error": [
    "Please enter the correct email address."
  ]
}
```

### HTTP Request

`POST http://baseurl/api/signin`


Parameter | Type    | Description | Required
--------- | ------- | ------------|----------
email     |  string | Email address of the user|true
password  |  string | Password of the user|true

<aside class="success">status:200 OK </aside>
<aside class="warning">status:422 Unprocessable entry.</aside>

## Login with Facebook

This API is used for login with Facebook. 

```shell
curl -X POST \
http://baseurl/api/signin \
-H 'accept: application/json' \
-H 'cache-control: no-cache' \
-H 'content-type: application/json' \
-d '{
"user" :{
"facebook" :"true",
"token": "facebooktoken",
 }
}'
 ```


> The above command returns JSON structured like this:

```json
{
	"user": {
		"id": 57,
		"fname": "vikram",
		"lname": null,
		"company_name": null,
		"company_title": null,
		"street": null,
		"unit": null,
		"street_name": null,
		"city": null,
		"state": null,
		"country": null,
		"pin": null,
		"email": "vikamsharma@gmail.com",
		"phone": null,
		"fax": null,
		"created_at": "2017-09-21 11:32:55",
		"updated_at": "2017-09-21 11:32:55"
	},
	"access_token": "ABCABCABC",
    "refresh_token": "DEFDEFDEF"
}
```
```json
{
  "error": [
    "Email and password not correct"
  ]
}
```

### HTTP Request

`POST http://baseurl/api/signin`


Parameter | Type    | Description | Required
--------- | ------- | -----------|------------
facebook  | boolean | Facebook value of the user	| true
token	  | string	| Token of the user	true | true	

<aside class="success">status:200 OK </aside>
<aside class="warning">status:422 Unprocessable entry.</aside>

## Login with Google

This API is used for login with Google.

```shell
curl -X POST \
http://baseurl/api/signin \
-H 'accept: application/json' \
-H 'cache-control: no-cache' \
-H 'content-type: application/json' \
-d '{
"user" :{
"google" :"true",
"token": "googletoken",
 }
}'
 ```


> The above command returns JSON structured like this:

```json
{
	"user": {
		"id": 57,
		"fname": "vikram",
		"lname": null,
		"company_name": null,
		"company_title": null,
		"street": null,
		"unit": null,
		"street_name": null,
		"city": null,
		"state": null,
		"country": null,
		"pin": null,
		"email": "vikamsharma@gmail.com",
		"phone": null,
		"fax": null,
		"created_at": "2017-09-21 11:32:55",
		"updated_at": "2017-09-21 11:32:55"
	},
	"access_token": "ABCABCABC",
    "refresh_token": "DEFDEFDEF"
}
```


### HTTP Request

`POST http://baseurl/api/signin`

Parameter | Type    | Description | Required 
--------- | ------- | ----------- |----------
google    | boolean | Google value of the user | true	
token	  | string	| Token of the user	true | true

<aside class="success">status:200 OK </aside>
<aside class="warning">status:422 Unprocessable entry.</aside>

## Forgot Password

This API is used for forgot password.

```shell
curl -X POST \
http://baseurl/api/reset-password\
-H 'accept: application/json' \
-H 'cache-control: no-cache' \
-H 'content-type: application/json' \
-d '{
"user":
{
"email":"rajeshkumar@gmail.com"
}
}

 ```


> The above command returns JSON structured like this:

```json
 {
   "message" : "Password sent on your email" 
 }
```
```json
{
  "error": [
    "This email is not register. Please sign up."
  ]
}
```

### HTTP Request

`POST http://baseurl/api/reset-password`


Parameter | Type    | Description | Required 
--------- | ------- | -----------|------------
email	|string	   |Email address of the user |	true

<aside class="success">status:200 OK </aside>
<aside class="warning">status:422 Unprocessable entry.</aside>


##Retrieve access token

This API is used for retrieve access token.

```shell
 curl -X POST \
 http://baseurl/api/refresh_token \
 -H 'accept: application/json' \
 -H 'cache-control: no-cache' \
 -H 'content-type: application/json' \
 -d '{
 "user" :{
 "refresh_token" :"ABCABCABC",
  }
 }'

 ```


> The above command returns JSON structured like this:

```json
{
	"user": {
		"id": 57,
		"fname": "vikram",
		"lname": null,
		"company_name": null,
		"company_title": null,
		"street": null,
		"unit": null,
		"street_name": null,
		"city": null,
		"state": null,
		"country": null,
		"pin": null,
		"email": "vikamsharma@gmail.com",
		"phone": null,
		"fax": null,
		"created_at": "2017-09-21 11:32:55",
		"updated_at": "2017-09-21 11:32:55"
	},
	"access_token": "ABCABCABC",
    "refresh_token": "DEFDEFDEF"
}
```



### HTTP Request

`POST http://baseurl/api/refresh_token`


Parameter | Type    | Description | Required 
--------- | ------- | -----------|------------
refresh_token| string |	true  |Refresh token of the user	

<aside class="success">status:200 OK </aside>
<aside class="warning">status:422 Unprocessable entry.</aside>