Float Holidays
==============

Get Holidays
------------

Return all account holidays.

    `GET /holidays` will return all holidays
    
A sample response:

```
[
{
  holiday_id: "1533",
  holiday_name: "April Fool's Day",
  date: "2014-04-01",
  date_doy: "31"
}
]
```

Get Holiday
-----------

Return a specific holiday identified by the holiday id.

    `GET /holidays/1533` will return the specific holiday with the id 1533.
    
A sample response:

```
[
{
  holiday_id: "1533",
  holiday_name: "April Fool's Day",
  date: "2014-04-01",
  date_doy: "31"
}
]
```

Add Holiday
-----------

Add a new holiday within your existing account.

    `POST /holidays`
  
```
{
  holiday_name: "Memorial Day",
  date: "2014-05-26",
}
```

A successful addition will return a `201 Created` response.

Update Holiday
--------------

Update an existing holiday within your account.

    `PUT /holidays/1533` will update the holiday with the id 1533.

```
{
  holiday_name: "Updated Holiday Name",
  date: "2014-04-05",
}
```

Delete Holiday
--------------

This will delete a specific holiday.

    `DELETE /holidays/1533` will delete the task with the id 1533.
    
On success this will return a `200 Ok` response.
