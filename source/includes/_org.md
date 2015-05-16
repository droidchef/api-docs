# Organizations

## List Offices

```shell
curl "https://DomainName/api/v1/offices"
  -H "Authorization: Basic meowmeowmeow"
```

> The above command returns JSON structured like this:

```json
[
  {
        "id": 1,
        "name": "Head Office",
        "nameDecorated": "Head Office",
        "externalId": "1",
        "openingDate": [
            2009,
            1,
            1
        ],
        "hierarchy": "."
    }
]
```

This endpoint returns list of offices.

### HTTP Request

`GET https://DomainName/api/v1/offices`
## Get Offices Details  

```shell
curl "https://DomainName/api/v1/offices/template"
  -H "Authorization: Basic meowmeowmeow"
```

> The above command returns JSON structured like this:

```json
{
    "openingDate": [
        2013,
        2,
        4
    ],
    "allowedParents": [
        {
            "id": 1,
            "name": "Head Office",
            "nameDecorated": "Head Office"
        }
    ]
}
```

This is a convenience resource. It can be useful when building maintenance user interface screens for client applications. The template data returned consists of any or all of:

1)Field Defaults

2)Allowed Value List

### HTTP Request  

`GET https://DomainName/api/v1/offices`

## Retrieve an Office

```shell
curl "https://DomainName/api/v1/offices/1"
  -H "Authorization: Basic meowmeowmeow"
```

> The above command returns JSON structured like this:

```json
{
    "id": 1,
    "name": "Head Office",
    "nameDecorated": "Head Office",
    "externalId": "1",
    "openingDate": [
        2009,
        1,
        1
    ],
    "hierarchy": "."
}
```

This request is used to retrieve list of offices

### HTTP Request

`GET https://DomainName/api/v1/offices/1`

## Create an office

```shell
curl "http://domain.com/api/v1/questions"
  -X POST
  -H "X-Authorization: Basic meowmeowmeow"
  -H "Content-Type: application/json"
  -H "Accept: application/json"
  -d "{
    "name": "Example New Branch",
    "dateFormat": "dd MMMM yyyy",
    "locale": "en",
    "openingDate": "01 July 2007",
    "parentId": 2,
    "externalId": "SYS54-88"
}"
```

> The above command returns JSON structured like this:

```json
{
    "officeId": 3,
    "resourceId": 3
}
```

| Mandatory Fields|
| -------------   |
| name            |
| openingDate     |
| parentId        |

### HTTP Request

`POST https://DomainName/api/v1/offices`

## Update Office

```shell
curl "http://domain.com/api/v1/questions"
  -X PUT
  -H "X-Authorization: Basic meowmeowmeow"
  -H "Content-Type: application/json"
  -H "Accept: application/json"
  -d "{
	"name": "Name is updated"
}"
```

> The above command returns JSON structured like this:

```json
{
    "officeId": 1,
    "resourceId": 1,
    "changes": {
        "name": "Name is updated"
    }
}

```

This request is used to Update an office

### HTTP Request

`PUT https://DomainName/api/v1/offices/{officeId}`