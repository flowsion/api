Float Projects
==============

Get Projects
------------

This will return all account Projects.

    `GET /projects` will return all active projects
    `GET /projects/archived` will return all archived projects
    
A sample response:

```
[40]
0:  {
  project_id: "17740"
  project_name: "Website"
  vacation: "0"
  color: "0095D8"
  client_id: null
  client_name: null
}-
1:  {
  project_id: "14069"
  project_name: "iPhone Application"
  vacation: "0"
  color: "f982cb"
  client_id: null
  client_name: null
}
```

Get Project
-----------

This will return a specific project identified by the Project ID.

    `GET /projects/1` will return the specific project with the ID 1.
    
A sample response:
```
{
  project_id: "1",
  project_name: "Microsite",
  vacation: "0",
  color: "7448d2",
  client_id: "3",
  client_name: "Joe's Wares"
}
```

Create Project
--------------

This will create a new project within your existing account.

    `POST /projects`
  
```
{
  project_name: "Texas Ranger Site",
  color: "7448d2",
  client_name: "Walker"
}
```

On success this will return a `201 Created` response.

Update Project
--------------

This will update an existing project within your account.

    `PUT /projects/1` will update the project with the ID 1.

```
{
  project_name: "New Site Name",
  color: "7448d2",
  client_name: "New Client Name"
}
```
  
Archiving or Returning to Active Projects
-----------------------------------------

This will either archive or return to active a specified project.

    `PUT /projects/1` will archive Project ID 1.
    
```
{
  archived: "true"
}
```

Change true to false to return the project to active.

Delete Project
--------------

This will delete a specific project.

    `DELETE /projects/1` will delete the project with the ID 1.
    
On success this will return a `204 No Content` response.
