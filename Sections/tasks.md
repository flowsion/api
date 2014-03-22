Float Tasks
===========


Get Tasks
---------

	GET /tasks
will return all active tasks.

    
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
            "project_id": "364",
            "client_name": "Violet City",
            "creation_doy": "10",
            "start_date": "2014-03-17",
            "start_doy": "76",
            "start_yr": "2014",
            "end_date": "2014-03-21",
            "end_doy": "80",
            "hours_pd": "8.0",
            "total_hours": "40.0",
            "task_days": "5",
            "task_cal_days": "5",
            "created_by": "Glenn Baron",
            "creator_id": "135",
            "modified_by": "Glenn Baron",
            "project_name": "iPhone App",
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

Get Task
--------

Return a specific task identified by the task id.

	GET /tasks/123434
will return the specific task with the id 123.
    
A sample response:

```json
{
    "task_id": "214809",
    "task_name": "User Experience",
    "task_notes": "Reference wireframes doc.",
    "people_id": "236",
    "project_id": "364",
    "client_name": "Violet City",
    "creation_doy": "10",
    "start_date": "2014-03-17",
    "start_doy": "76",
    "start_yr": "2014",
    "end_date": "2014-03-21",
    "end_doy": "80",
    "hours_pd": "8.0",
    "total_hours": "40.0",
    "task_days": "5",
    "task_cal_days": "5",
    "created_by": "Glenn Baron",
    "creator_id": "135",
    "modified_by": "Glenn Baron",
    "project_name": "iPhone App",
    "priority": 0,

}
```

Add Task
--------

Add a new task within your existing account.

    POST /tasks
POST requests must be _application/x-www-form-urlencoded_ in name/value pairs. Data must also be URL encoded as appropriate.

Sample request:

	task_name=Design&people_id=123&project_id=364&client_name=Violet&creation_doy=10&start_date=2014-03-17&start_doy=76&start_yr=2014&end_date=2014-03-21&end_doy=80&hours_pd=8.0&total_hours=40&task_days=5&task_cal_days=5&priority=1

Valid fields with example values:

    task_name=Design
    people_id=123
    project_id=364
    client_name=Violet
    creation_doy=10
    start_date=2014-03-17
    start_doy=76
    start_yr=2014
    end_date=2014-03-21
    end_doy=80
    hours_pd=8.0
    total_hours=40
    task_days=5
    task_cal_days=5
    priority=1
    
A successful create record will return a `201 Created` response status with the new id:

```json
{
	"task_id":"34342"
}
```

Update Task
-----------

Update an existing person within your account.

    PUT /tasks/343444
will update the task with the id 343444.
PUT requests must be _application/x-www-form-urlencoded_ in name/value pairs. Data must also be URL encoded as appropriate.

	Update format and field values are the same as create, see above.

A successful update will return a `200 Ok` response status.

Delete Task
-----------

Delete a specific task.

    DELETE /people/343444
will delete the task with the id 343444. _Warning: deletes can not be undone and data can not be recovered, please use with care._
    
A successful delete will return a `200 Ok` response status.
