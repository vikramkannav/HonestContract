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
{
"contract":
{
"name":"Sony TV 100",
"type":"buyer",
"buyer_country":"India",
"seller_country":"",
"invitation_to":"jams"
}}}

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

`POST http://example.com/contract`


Parameter | Type    | Description | Required
--------- | ------- | ----------- |-----------
name | string | Name of the contract | true
type| string  | Type seller or buyer | true
buyer_country |string | Buyer country name | true
seller_country | string| Seller Country name | true
invitation_to | string | Invitation person information|true 


##Contract List

This API is used for the contracts list of the he/she(users).

```shell
curl "http://example.com/contracts"
 ```

> The above command returns JSON structured like this:

```json

{
	"contract": {
		"name": "Sony TV 100",
		}
}



```

### HTTP Request

`GET http://example.com/contracts`


Parameter | Type    | Description | Required
--------- | ------- | ----------- |-----------




## Purpose 
This API is use for create the Purpose .

```shell
curl "http://example.com/contract/:id/puprpose"
 ```

> The above command returns JSON structured like this:

```json
```

### HTTP Request

`POST http://example.com/contract/:id/purpose`


Parameter | Type    | Description | Required
--------- | ------- | ----------- |-----------
contract_id | integer | Id of the contract | true
purpose    |  string | Purpose description | true
units_to_be_sold| integers  | Units of the purpose | true
purpose_image| image | Multiple Image of the purpose| true
description  | pdf | Description of the purpose | true
agreement | pdf | Agreement of the purpose  | true
status     | tinyInteger | Status of the purpose | true

## Termination

This API is used for create the termination of the contract.

```shell
curl "http://example.com/contract/:id/termination"
 ```

> The above command returns JSON structured like this:

```json
```

### HTTP Request

`POST http://example.com/contract/:id/termination`


Parameter | Type    | Description | Required 
--------- | ------- | ----------- |--------
contract_id | integer | Id of the contract   | true
terminated_by| enum   | Terminated by options|
target_not_meet| enum | Target not meet option|
inform_days | integer| Inform days of termination|
status     | tinyInteger | Status of the termination | true
            




## Renewal

This API is used for the renewal the contract.

```shell
curl "http://example.com/contract/:id/renewal"
 ```


> The above command returns JSON structured like this:

```json
```


### HTTP Request

`POST http://example.com/contract/:id/renewal`


Parameter | Type     | Description | Required
--------- | ---------| -----------|-------------
contract_id | integer | Id of the contract | true
type        | json    | Renewal type of contract| true
informed_period| integer| Renewal Informed period time | true
inform_days |  integer | Renewal Inform days | true
status     | tinyInteger | Status of the Renewal | true


## Message

This API is used for the message for the purpose.

```shell
curl "http://example.com/purpose/:id/message"
 ```


> The above command returns JSON structured like this:

```json
```


### HTTP Request

`POST http://example.com/purpose/:id/message`


Parameter | Type     | Description | Required
--------- | ---------| -----------|-------------
purpose_id | integer | Id of the purpose | true
description| string | Description of the message | true
