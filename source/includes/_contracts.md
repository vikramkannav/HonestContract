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
        "name": "Sony TV 100",
	    "buyer_id": "1",
		"seller_id": "2",
		"buyer_country":"India",
        "seller_country":"China",
		"status": "1"
}}
```

> The above command returns JSON structured like this:

```json
{
	"contract": {
		 "name": "Sony TV 100",
         "buyer_id": "1",
         "seller_id": "2",
         "buyer_country":"India",
         "seller_country":"China",
         "status": "1"
	}
}
```

### HTTP Request

`POST http://baseurl/contract`


Parameter | Type    | Description | Required
--------- | ------- | ----------- |-----------
name | string | Name of the contract | true



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
          "buyer_id": "1",
          "seller_seller": "2",
          "buyer_country":"India",
          "seller_country":"China",
          "status": "1"
		},
		{
		  "name": "LG TV 50",
		   "buyer_id": "1",
           "seller_seller": "4",
           "buyer_country":"India",
            "seller_country":"US",
            "status": "1"
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
"status":"1"
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
		"status": "1"
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
status     | tinyInteger | Status of the purpose | true

<aside class="success">status:200 OK </aside>
<aside class="warning">status:422 Unprocessable entry.</aside>

## Product & Price

This API is used for product and price of the contract.

```shell
curl -X POST \
http://baseurl/contract/:id/product_price \
-H 'accept: application/json' \
-H 'cache-control: no-cache' \
-H 'content-type: application/json' \
-d ' {
     	"product_price": {
     		"units_sold": "15",
     		"price_per_unit": "100",
     		"discount_percentage": "10",
     		"taxes_amount": "2",
     		"shipping_cost": "20",
     		"total_price": "147",
     		"export_charge": "buyer",
     		"import_charge": "buyer & seller",
     		"terms": "document.pdf",
     		"status": "1"
     	}
     }
 ```

> The above command returns JSON structured like this:

```json
    {
    	"product_price": {
    		"units_sold": "15",
    		"price_per_unit": "100",
    		"discount_percentage": "10",
    		"taxes_amount": "2",
    		"shipping_cost": "20",
    		"total_price": "147",
    		"export_charge": "buyer",
    		"import_charge": "buyer & seller",
    		"terms": "document.pdf",
    		"status": "1"
    	}
    }
```

### HTTP Request

`POST http://baseurl/contract/:id/product_price`


Parameter | Type    | Description | Required 
--------- | ------- | ----------- |--------
units_sold| integer | Units to be sold |
price_per_unit |  integer | Price per unit  |
discount_percentage | integer | Discount given |
taxes |  integer | Amount of tax |
shipping_cost | integer | Amount for shipping cost|
total_price | integer | Total price with tax and discount|
export_charge | tinyInteger | Export charge paid by
import_charge |tinyInteger | Import charge paid by
terms  |  pdf    | Term document of payment & price
status |tinyInteger |Status of the product and price


<aside class="success">status:200 OK </aside>
<aside class="warning">status:422 Unprocessable entry.</aside>

## Payment

This API is used for payment of the contract.

```shell
curl -X POST \
http://baseurl/contract/:id/payment \
-H 'accept: application/json' \
-H 'cache-control: no-cache' \
-H 'content-type: application/json' \
-d ' {
 	"payment": {
 		"timing_payment": "3",
 		"timing_other": "",
 		"late_charge": "",
 		"payment_method": "2",
 		"payment_other":"" ,
 		"status": "1"
 	}
 }
```

> The above command returns JSON structured like this:

```json
{
	"payment": {
		"timing_payment": "3",
		"timing_other": "",
		"late_charge": "",
		"payment_method": "2",
		"payment_other":"" ,
		"status": "1"
	}
}
 ```

### HTTP Request

`POST http://baseurl/contract/:id/payment`


Parameter | Type    | Description | Required 
--------- | ------- | ----------- |--------
timing_payment|tinyInteger| Timing payment option |
timing_other| string |  Timing other payment option |
late_charge| integer | Late charges in payment |
payment_method | tinyInteger | Payment method |
payment_other | string | Payment other Method |
status| tinyInteger | Status of payment |

<aside class="success">status:200 OK </aside>
<aside class="warning">status:422 Unprocessable entry.</aside>



## Shipping

This API is used for shiping of the contract.

```shell
curl -X POST \
http://baseurl/contract/:id/payment \
-H 'accept: application/json' \
-H 'cache-control: no-cache' \
-H 'content-type: application/json' \
-d ' {
 	"shipping": {
  	}
 }
```

> The above command returns JSON structured like this:

```json
{
	"shipping": {
	}
}
 ```

### HTTP Request

`POST http://baseurl/contract/:id/payment`


Parameter | Type    | Description | Required 
--------- | ------- | ----------- |--------
shipping_time|tinyInteger| Shipping time option |
shipping_time_other|string| Shipping time other option |
purpose_title|tinyInteger| Purpose of title
transport_option |tinyInteger|Transport option 
shipping_cost| integer | Buyer pay shipping cost
destination| string |Destination of the shipping |
insurance_amount| integer | Insure loss up following amount
freight | string | Freight | Freight option
shipping_instruction| pdf  | Shipping instruction 
status| tinyInteger | Status of shipping | 

<aside class="success">status:200 OK </aside>
<aside class="warning">status:422 Unprocessable entry.</aside>



## Final Agreement

This API is used for the final agreement of the contract.

```shell
curl -X POST \
http://baseurl/contract/:id/final \
-H 'accept: application/json' \
-H 'cache-control: no-cache' \
-H 'content-type: application/json' \
-d ' {
 	"final": {
  	}
 }
```

> The above command returns JSON structured like this:

```json
{
	"final": {
	}
}
 ```

### HTTP Request

`POST http://baseurl/contract/:id/final`


Parameter | Type    | Description | Required 
--------- | ------- | ----------- |--------
event_of_breach | boolean | Event breach option |
liability_option |tinyInteger| Liability option of the final
country |  string  | Agreement follow country law |
state |  string  | Agreement follow state law |
binding_arbitation | tinyInteger | Arbitation following body
litigation_by |tinyInteger| Litigation option |
dispute_arising |boolean| Any dispute arising |
additional_term| pdf  | Additional term option |
status| tinyInteger | Status of payment |

<aside class="success">status:200 OK </aside>
<aside class="warning">status:422 Unprocessable entry.</aside>






























