Holidays
========

Get Holidays
------------

	GET /holidays
will return all holidays.

    
A sample response:
```json
{
        "holiday_id": "1533",
        "holiday_name": "April Fool's Day",
        "date": "2014-04-01",
        "date_doy": "31"
        },
        {
        "holiday_id": "1534",
        "holiday_name": "Independence Day",
        "date": "2014-07-04",
        "date_doy": "55"
        ...
}
```

Get Holiday
-----------

Return a specific holiday identified by the holiday id.

	GET /holidays/1533
will return the specific holiday with the id 1533.
    
A sample response:

```json
{
    "holiday_id": "1533",
    "holiday_name": "April Fool's Day",
    "date": "2014-04-01",
    "date_doy": "31"
}
```

Add Holiday
-----------

Add a new holiday within your existing account.

    POST /holidays
POST requests must be _application/x-www-form-urlencoded_ in name/value pairs. Data must also be URL encoded as appropriate.

Sample request:

	holiday_name=New_Holiday&date=2014-07-01

Valid fields with example values:

    holiday_name=New Holiday
    date=2014-07-01

A successful create record will return a `201 Created` response status with the new id:

```json
{
	"holiday_id":"1536"
}
```

Update Holiday
--------------

Update an existing holiday within your account.

    PUT /holidays/2324
will update the holiday with the id 2324.
PUT requests must be _application/x-www-form-urlencoded_ in name/value pairs. Data must also be URL encoded as appropriate.

	Update format and field values are the same as create, see above.

A successful update will return a `200 Ok` response status.

Delete Holiday
--------------

Delete a specific holiday.

    DELETE /holidays/2324
will delete the holiday with the id 2324. _Warning: deletes can not be undone and data can not be recovered, please use with care._
    
A successful delete will return a `200 Ok` response status.
