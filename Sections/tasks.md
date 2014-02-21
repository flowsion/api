Float Tasks
===========

Get Task
--------

Return all account tasks.

    `GET /tasks` will return all tasks
    
A sample response:

```
{
  position: "full",
  start_doy: "26",
  start_yr: "2014",
  people: [
{
  people_id: "246",
  tasks: [
  {
    task_id: "252806",
    task_name: "Design",
    people_id: "1",
    project_id: "880",
    client_name: "Happy times",
    week_start_date: "2014-02-16",
    creation_doy: "48",
    start_date: "2014-02-17",
    start_doy: "48",
    start_yr: "2014",
    end_date: "2014-02-27",
    end_doy: "58",
    block_start_date: "2014-02-17",
    block_start_doy: "48",
    block_end_doy: "52",
    block_end_date: "2014-02-21",
    block_len: "5",
    hours_pd: "2.0",
    total_hours: "18.0",
    task_days: "9",
    task_cal_days: "11",
    created_by: "Glenn Rogers",
    creator_id: "2",
    modified_by: "Glenn Rogers",
    project_name: "My New Project",
    sked_admin: "true",
    is_owner: "true",
    priority: 0
},
```

Get Task
--------

Return a specific task identified by the task id.

    `GET /tasks/142425` will return the specific task with the id 142425.
    
A sample response:

```
{
  task_id: "142425",
  task_name: "Art Direction",
  people_id: "259",
  project_id: "38",
  client_name: "Walker",
  week_start_date: "2014-01-26",
  creation_doy: "339",
  start_date: "2014-02-12",
  start_doy: "43",
  start_yr: "2014",
  end_date: "2014-02-18",
  end_doy: "49",
  hours_pd: "8.0",
  total_hours: "40.0",
  task_days: "5",
  task_cal_days: "7",
  created_by: "Glenn Rogers",
  creator_id: "2",
  modified_by: "Glenn Rogers",
  project_name: "Nylon",
  sked_admin: "true",
  is_owner: "true",
  priority: 1
}
```

Add Task
--------

Add a new task within your existing account.

    `POST /tasks`
  
```
{
  task_name: "Design",
  people_id: "259",
  project_id: "38",
  client_name: "Walker",
  week_start_date: "2014-01-26",
  creation_doy: "339",
  start_date: "2014-02-12",
  start_doy: "43",
  start_yr: "2014",
  end_date: "2014-02-18",
  end_doy: "49",
  hours_pd: "8.0",
  total_hours: "40.0",
  task_days: "5",
  task_cal_days: "7",
  created_by: "Glenn Rogers",
  creator_id: "2",
  modified_by: "Glenn Rogers",
  project_name: "Nylon",
  sked_admin: "true",
  is_owner: "true",
}
```

A successful addition will return a `201 Created` response.

Update Task
-----------

Update an existing task within your account.

    `PUT /tasks/1` will update the person with the id 1.

```
{
  task_id: "142425",
  task_name: "New Task Name",
}
```

Delete Task
-----------

This will delete a specific task.

    `DELETE /tasks/142425` will delete the task with the id 142425.
    
On success this will return a `200 Ok` response.
