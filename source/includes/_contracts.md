# Contracts

##Create Contract
With this API he/she can create his/her contract through his/her company.

```shell
curl -X POST \
http://baseurl/contract \
-H 'accept: application/json' \
-H 'cache-control: no-cache' \
-H 'content-type: application/json' \
-d '{
"contract":
{
"name":"Sony TV 100",
"type":"buyer",
"buyer_country":"India",
"seller_country":"",
"invitation_to":"jams"
}}
```

> The above command returns JSON structured like this:

```json
{
	"contract": {
		"name": "Sony TV 100",
		"type": "buyer",
		"buyer_country": "India",
		"seller_country": "",
		"invitation_to": "jams"
	}
}
```

### HTTP Request

`POST http://baseurl/contract`


Parameter | Type    | Description | Required
--------- | ------- | ----------- |-----------
name | string | Name of the contract | true
type| string  | Type seller or buyer | true
buyer_country |string | Buyer country name | true
seller_country | string| Seller Country name | true
invitation_to | string | Invitation person information|true 


<aside class="success">status:200 OK </aside>
<aside class="warning">status:422 Unprocessable entry.</aside>


##Contract List

This API is used for the contracts list of the he/she (user).

```shell
curl -X GET \
http://baseurl/contracts \
-H 'accept: application/json' \
-H 'cache-control: no-cache' \
-H 'content-type: application/json' \
-d '{
}
 ```

> The above command returns JSON structured like this:

```json
{
	"contracts": [{
			"name": "Sony TV 100",
			"type": "buyer",
			"buyer_country": "India",
			"seller_country": "",
			"invitation_to": "jams"
		},
		{
			"name": "LG TV 50",
			"type": "buyer",
			"buyer_country": "India",
			"seller_country": "",
			"invitation_to": "Raymond"
		}
	]
}

```

### HTTP Request

`GET http://baseurl/contracts`


Parameter | Type    | Description | Required
--------- | ------- | ----------- |-----------
          |         |             | 
          |         |             |


<aside class="success">status:200 OK </aside>


## Purpose 
This API is used for create the purpose.

```shell
curl -X POST \
http://baseurl/contract/:id/purpose \
-H 'accept: application/json' \
-H 'cache-control: no-cache' \
-H 'content-type: application/json' \
-d '{
"purposes" : {
"purpose":"Remote TV",
"units_to_be_sold":"20",
"purpose_image":"Remote.png",
"description":"description.pdf"",
"agreement":"agreement.pdf",
"status":""
}}
 ```

> The above command returns JSON structured like this:

```json
{
	"purpose": {
		"purpose": "Remote TV",
		"units_to_be_sold": "20",
		"purpose_image": "Remote.png",
		"description": "description.pdf",
		"agreement": "agreement.pdf",
		"status": ""
	}
}
```

### HTTP Request

`POST http://baseurl/contract/:id/purpose`


Parameter | Type    | Description | Required
--------- | ------- | ----------- |-----------
purpose    |  string | Purpose description | true
units_to_be_sold| integers  | Units of the purpose | true
purpose_image| image | Multiple Image of the purpose| true
description  | pdf | Description of the purpose | true
agreement | pdf | Agreement of the purpose  | true
status     | tinyInteger | Status of the purpose | true

<aside class="success">status:200 OK </aside>
<aside class="warning">status:422 Unprocessable entry.</aside>

## Termination

This API is used for create the termination of the contract.

```shell
curl -X POST \
http://baseurl/contract/:id/termination \
-H 'accept: application/json' \
-H 'cache-control: no-cache' \
-H 'content-type: application/json' \
-d '{
"terminations" :{
"terminated_type":"",
"target_not_meet":"",
"inform_days":"",
"status":"",
"status":""
 }
}
 ```

> The above command returns JSON structured like this:

```json
{
"terminations":{
"terminated_type":"",
"target_not_meet":"",
"inform_days":"",
"status":""
 }
}
```

### HTTP Request

`POST http://baseurl/contract/:id/termination`


Parameter | Type    | Description | Required 
--------- | ------- | ----------- |--------
terminated_type| enum   | Terminated type by options|
target_not_meet| enum | Target not meet option|
inform_days | integer| Inform days of termination|
status     | tinyInteger | Status of the termination | true
            

<aside class="success">status:200 OK </aside>
<aside class="warning">status:422 Unprocessable entry.</aside>


## Renewal

This API is used for the renewal the contract.

```shell
curl -X POST \
http://baseurl/contract/:id/renewal \
-H 'accept: application/json' \
-H 'cache-control: no-cache' \
-H 'content-type: application/json' \
-d '{
"renewal":{
"type":"",
"informed_period":"",
"inform_days":"",
"status":""
 }
}
```


> The above command returns JSON structured like this:

```json
{
	"renewal": {
	    "type": "",
		"informed_period": "",
		"inform_days": "",
		"status": ""
	}
}
```


### HTTP Request

`POST http://baseurl/contract/:id/renewal`


Parameter | Type     | Description | Required
--------- | ---------| -----------|-------------
type        | json    | Renewal type of contract| true
informed_period| integer| Renewal Informed period time | true
inform_days |  integer | Renewal Inform days | true
status     | tinyInteger | Status of the Renewal | true

<aside class="success">status:200 OK </aside>
<aside class="warning">status:422 Unprocessable entry.</aside>

## Message

This API is used for the message for the purpose.

```shell
curl -X POST \
http://baseurl/purpose/:id/message\
-H 'accept: application/json' \
-H 'cache-control: no-cache' \
-H 'content-type: application/json' \
-d '{
{
  "messgae":{
  "description":"message";
 }
}


 ```


> The above command returns JSON structured like this:

```json
{
  "messgae":{
  "description":"message"
 }
}
```


### HTTP Request

`POST http://baseurl/purpose/:id/message`


Parameter | Type     | Description | Required
--------- | ---------| -----------|-------------
description| string | Description of the message | true

<aside class="success">status:200 OK </aside>
<aside class="warning">status:422 Unprocessable entry.</aside>