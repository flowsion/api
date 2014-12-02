Float Tasks
===========


Get Tasks
---------

	GET /tasks
Will return all active tasks that occur within a given time period. 
Default time period is 13 weeks. Default start period is the first full week prior to the start day, which defaults to today, if no attribute is passed.

    
A sample response:

```json
{
    "position": "full",
    "start_doy": "75",
    "start_yr": "2014",
    "people": [
    {
        "people_id": "236",
        "tasks":
        {
            "task_id": "214809",
            "task_name": "Design",
            "task_notes": "See related ticket.",
            "people_id": "236",
            "person_name:": "Paul Artisen",
            "project_id": "364",
            "project_name": "Microsite",
            "client_name": "Violet City",
            "start_date": "2014-03-17",
            "start_yr": "2014",
            "end_date": "2014-03-21",
            "hours_pd": "8.0",
            "total_hours": "40.0",
            "task_days": "5",
            "task_cal_days": "5",
            "created_by": "Glenn Baron",
            "creator_id": "135",
            "modified_by": "Glenn Baron",
            "priority": 0,
        }
        {
            "task_id": "283660",
            "task_name": "Art Direction",
            "task_notes": null,
            "people_id": "236",
            "project_id": "364",
            "client_name": "Violet City",
        ...
}
```

<b>Filters for /tasks </b>
Valid fields with example values:

    start_day=2015-01-01
    weeks=13
    people_id=12345


Get Task
--------

Return a specific task identified by the task id.

	GET /tasks/123434
will return the specific task with the id 123434.
    
A sample response:

```json
{
    "task_id": "123434",
    "task_name": "User Experience",
    "task_notes": "Reference wireframes doc.",
    "people_id": "236",
    "person_name:": "Paul Artisen",
    "project_id": "364",
    "project_name": "Microsite",
    "client_name": "Violet City",
    "start_date": "2014-03-17",
    "start_yr": "2014",
    "end_date": "2014-03-21",
    "hours_pd": "8.0",
    "total_hours": "40.0",
    "task_days": "5",
    "task_cal_days": "5",
    "created_by": "Glenn Baron",
    "creator_id": "135",
    "modified_by": "Glenn Baron",
    "priority": 0,

}
```

Add Task
--------

Add a new task within your existing account.

    POST /tasks
POST requests must be _application/x-www-form-urlencoded_ in name/value pairs. Data must also be URL encoded as appropriate.

Sample request:

	task_name=Design&people_id=123&project_id=364&start_date=2014-03-17&end_date=2014-03-21&hours_pd=8.0&priority=1

Required fields with example values:

    people_id=123
    project_id=364
    start_date=2014-03-17
    end_date=2014-03-21
    hours_pd=8
    
A successful create record will return a `201 Created` response status with the new id:

```json
{
	"task_id":"34342"
}
```

Update Task
-----------

Update an existing task within your account.

    PUT /tasks/343444
will update the task with the id 343444.
PUT requests must be _application/x-www-form-urlencoded_ in name/value pairs. Data must also be URL encoded as appropriate.

	Update format and field values are the same as create, see above.

A successful update will return a `200 Ok` response status.

Delete Task
-----------

Delete a specific task.

    DELETE /tasks/343444
will delete the task with the id 343444. _Warning: deletes can not be undone and data can not be recovered, please use with care._
    
A successful delete will return a `200 Ok` response status.
