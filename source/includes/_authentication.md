# Authentication

## Signup

This API is used for the Signup with HonestContract application with some information.

```shell
 curl -X POST \
 http://baseurl/signup \
-H 'accept: application/json' \
-H 'cache-control: no-cache' \
-H 'content-type: application/json' \
-d '{
"users" :{
"name":"rajeshkumar",
"email": "rajeshkumar@gmail.com",
"password":"******"
}
}'
```

> The above command returns JSON structured like this:

```json
{
	"users": {
		"name": "rajeshkumar",
		"fname": "",
		"lname": "",
		"company_name": "",
		"company_title": "",
		"street": "",
		"unit": "",
		"street_name": "",
		"city": "",
		"state": "",
		"country": "",
		"pin": "",
		"email": "",
		"phone": "",
		"fax": "",
        "refresh_token": "ABCABCABC",
        "auth_token": "DEFDEFDEF"
	}
}

```


### HTTP Request

`POST http://baseurl/signup`


Parameter | Type    | Description | Required
--------- | ------- | ----------- | -----------
name     | string   | Name of the user | true
email     | string  | Email address of the user | true
password  |  string | Password of the user | true
confirm_password  |  string | Password of the user | true


<aside class="success">Status code :200 OK </aside>
<aside class="warning">Error code : 422 Unprocessable Entity</aside>

## Sigin 

This API is used for the login with email and password.

```shell
curl -X POST \
http://baseurl/signin \
-H 'accept: application/json' \
-H 'cache-control: no-cache' \
-H 'content-type: application/json' \
-d '{
"users" :{
"email": "rajeshkumar@gmail.com",
"password" :"********",
}
}'

 ```


> The above command returns JSON structured like this:

```json
{
	"users": {
		"name": "rajeshkumar",
		"fname": "",
		"lname": "",
		"company_name": "",
		"company_title": "",
		"street": "",
		"unit": "",
		"street_name": "",
		"city": "",
		"state": "",
		"country": "",
		"pin": "",
		"email": "",
		"phone": "",
		"fax": ""
	},
	"refresh_token": "ABCABCABC",
	"auth_token": "DEFDEFDEF"
}

```


### HTTP Request

`POST http://baseurl/signin`


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
http://baseurl/signin \
-H 'accept: application/json' \
-H 'cache-control: no-cache' \
-H 'content-type: application/json' \
-d '{
"users" :{
"facebook" :"true",
"token": "facebooktoken",
 }
}'
 ```


> The above command returns JSON structured like this:

```json
{
	"users": {
		"name": "rajeshkumar",
		"fname": "",
		"lname": "",
		"company_name": "",
		"company_title": "",
		"street": "",
		"unit": "",
		"street_name": "",
		"city": "",
		"state": "",
		"country": "",
		"pin": "",
		"email": "",
		"phone": "",
		"fax": "",
		"refresh_token": "ABCABCABC",
       	"auth_token": "DEFDEFDEF"
     	}
}	

```


### HTTP Request

`POST http://baseurl/signin`


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
http://baseurl/signin \
-H 'accept: application/json' \
-H 'cache-control: no-cache' \
-H 'content-type: application/json' \
-d '{
"users" :{
"google" :"true",
"token": "googletoken",
 }
}'
 ```


> The above command returns JSON structured like this:

```json
{
	"users": {
		"name": "rajeshkumar",
		"fname": "",
		"lname": "",
		"company_name": "",
		"company_title": "",
		"street": "",
		"unit": "",
		"street_name": "",
		"city": "",
		"state": "",
		"country": "",
		"pin": "",
		"email": "",
		"phone": "",
		"fax": "",
		"refresh_token": "ABCABCABC",
       	"auth_token": "DEFDEFDEF"
	}
}
```


### HTTP Request

`POST http://baseurl/signin`

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
http://baseurl/forget \
-H 'accept: application/json' \
-H 'cache-control: no-cache' \
-H 'content-type: application/json' \
-d '{
"users":
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


### HTTP Request

`POST http://baseurl/forgot`


Parameter | Type    | Description | Required 
--------- | ------- | -----------|------------
email	|string	   |Email address of the user |	true

<aside class="success">status:200 OK </aside>
<aside class="warning">status:422 Unprocessable entry.</aside>


##Retrieve access token

This API is used for retrieve access token.

```shell
 curl -X POST \
 http://baseurl/refresh_token \
 -H 'accept: application/json' \
 -H 'cache-control: no-cache' \
 -H 'content-type: application/json' \
 -d '{
 "users" :{
 "refresh_token" :"ABCABCABC",
  }
 }'

 ```


> The above command returns JSON structured like this:

```json
{
	"users": {
		"fname": "Rajesh",
		"lname": "Kumar",
		"company_name": "Sony",
		"company_title": "Sony",
		"street": "44",
		"unit": "24",
		"street_name": "Sec 24",
		"city": "Gurgaon",
		"state": "Haryana",
		"country": "India",
		"pin": "110021",
		"email": "rajesh@gmail.com",
		"phone": "9898989898",
		"fax": "011-234446",
        "refresh_token": "NARNARNAR",
         "auth_token": "DEFDEFDEF" 
	}
}

```


### HTTP Request

`POST http://baseurl/refresh_token`


Parameter | Type    | Description | Required 
--------- | ------- | -----------|------------
refresh_token| string |	true  |Refresh token of the user	

<aside class="success">status:200 OK </aside>
<aside class="warning">status:422 Unprocessable entry.</aside>