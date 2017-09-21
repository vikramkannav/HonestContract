# User

## Update Profile

This API is used for the update profile with the HonestContract application with some information.

```shell
curl -X POST \
http://baseurl/api/user \
-H 'accept: application/json' \
-H 'cache-control: no-cache' \
-H 'content-type: application/json' \
-d '{
{
  "user":
    {
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
    "fax": "011-234446"
  }
}
}'
```


> The above command returns JSON structured like this:

```json
{
  "user":
    {
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
    "fax": "011-234446"
  }
}
```


### HTTP Request

`POST http://baseurl/api/user`


Parameter | Type    | Description | Required
--------- | ------- | ----------- | -----------
fname     | string | First name of the user | true
lname     | string  | Last name of the user | true
company_name| string | Company name          | true
company_title| string | Title of the company  | true
street    |integer     | Street number of the company |true
unit      | integer    | Unit of the company |true
street_name | string  | Street name of the company |true 
city      |  string | City nameof the company | true
state     |  string | State name of the company  | true
country   | string  | Country name of the Company | true
pin       |  int    | Postal code of the company | true
email     | string  | Email address of the user | true
password  |  string | Password of the user | true
phone     |  int    | phone number of the user | true
fax       | int     | Fax number of the company |strue


<aside class="success">Status code :200 OK </aside>
<aside class="warning">Error code : 422 Unprocessable Entity</aside>

