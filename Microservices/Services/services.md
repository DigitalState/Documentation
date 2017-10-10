# Services




# Service Type: BPM

### Server Validations


`GET: {{services}}{{environment}}/scenarios/d4833574-377f-4845-acc1-bc6fcead0ce5/submissions`

Headers:
- `Authorization: Bearer {{token}}`
- `Content-Type: application/json`
- `Accept: application/json`

Body:

```json
{
	"data": {
		"profilesector": "123",
		"email": "morgan@site.com",
		"posSerialnumber": "123",
		"amounttobepaid": 23
	}
}
```

Response:

```json
{
    "type": "https://tools.ietf.org/html/rfc2616#section-10",
    "title": "An error occurred",
    "detail": "data.firstName: \"firstName\" is required",
    "violations": [
        {
            "propertyPath": "data.firstName",
            "message": "\"firstName\" is required"
        }
    ]
}
```

Status Code: `400 Bad Request`

Context: The form has a field with the API name `firstName` which is marked as required.  This field is required on the client side and because all validations are also preformed on the server side, when a direct API call is made to make a submission, the `firstName` field is required as part of a server side validation.

The first server side validation that occurs is returned immediately to the requestor.   



# Service Design Consdierations

1. Scenarios should be linkable from the URL: Allowing a user in the browser to link directly to a scenario allows sharing of services and the specific scenario.