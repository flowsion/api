Time Off
========
The Float API supports:
- Time Off Types (e.g. Sick Leave, Paid Time Off, Holidays) **and**
- Time Off, the assignment of these Time Off Types to your team.

Get Time Off
------------

	GET /timeoffs
will return all scheduled time off.

    
A sample response:
```json
{
        "timeoff_id": "12333",
        "timeoff_type_id": "1533",
        "start_date": "2017-02-01",
        "end_date": "2017-02-02",
        "hours": "31",
        "timeoff_notes": "Not feeling well",
        "modified_by":"24998",
        "created_by":"24998",
        "created":"2017-02-01",
        "modified":"2017-02-01",
        "repeat_state":"0",
        "repeat_end":"0000-00-00",
        "full_day":null,
        "people_id":"51515"
},
{
        "timeoff_id": "12333",
        "timeoff_type_id": "1533",
        "start_date": "2017-02-04",
        "end_date": "2017-02-04",
        ...
}
```



Get Time Off
-----------

Return a specific time off identified by the time off id.

	GET /timeoffs/1533
will return the specific time off with the id 1533.
    
A sample response:

```json
{
        "timeoff_id": "12333",
        "timeoff_type_id": "1533",
        "start_date": "2017-02-04",
        "end_date": "2017-02-04",
}
```

Add Time Off
-----------

Assign time off within your existing account.

    POST /timeoffs
POST requests must be _application/x-www-form-urlencoded_ in name/value pairs. Data must also be URL encoded as appropriate.

Sample request:

	timeoff_type_id=2333&start_date=2014-07-01&end_date=2014-07-02&hours=8&timeoff_notes=Not%20feeling%20well&people_id=41444

Valid fields with example values:

    timeoff_type_id=2233
    start_date=2014-07-01
    end_date=2014-07-02
    hours=7.5
    people_id=23334

Full-day Time Off example values:

    timeoff_type_id=2233
    start_date=2014-07-01
    end_date=2014-07-02
    full_day=1
    people_id=23333

A successful create record will return a `201 Created` response status with the new id:

```json
{
	"timeoff_id":"1536"
}
```

Update Time Off
--------------

Update an existing time off within your account.

    PUT /timeoffs/2324
will update the time off with the id 2324.
PUT requests must be _application/x-www-form-urlencoded_ in name/value pairs. Data must also be URL encoded as appropriate.

	Update format and field values are the same as create, see above.

A successful update will return a `200 Ok` response status.

Delete Time Off
--------------

Delete a specific time off.

    DELETE /timeoffs/2324
will delete the time off with the id 2324. _Warning: deletes can not be undone and data can not be recovered, please use with care._
    
A successful delete will return a `200 Ok` response status.






Time Off Types
========

Time Off Types also support GET, POST, PUT and DELETE.

Get Time Off Types
-----------

	GET /timeoff_types

will return all Time Off Types

A sample response:

```json
{
        "timeoff_type_id": "20712",
        "timeoff_type_name": "Paid Time Off",
        "color": "1A90DB",
        "created_by": 23331
        },
        {
        "timeoff_type_id": "20713",
        "timeoff_type_name": "Sick Leave",
        "color": "DC164D",
        "created_by": 23331
        },
        {
        "timeoff_type_id": "20714",
        "timeoff_type_name": "Holiday",
        "color": "7D7D7D",
        "created_by": 23332
}
```

Add Time Off Types
-----------

Add Time Off Types within your existing account.

    POST /timeoff_types

Sample request:

	timeoff_type_name=Summer%20Fridays&color=AACB78

Valid fields with example values:

    timeoff_type_name=Summer%20Fridays
    color=AACB94

The account owner will be the default “created_by” account ID.

