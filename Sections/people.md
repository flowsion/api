Float People
============

Get People
----------

Return all account People.

    `GET /people` will return all active people
    `GET /projects/reserve` will return all people on the reserve
    
A sample response:

```
{
people: [
{
    people_id: "299",
    first_name: "Abel",
    last_name: "Anderson",
    job_title: "Designer",
    avatar_file: "avatar-299",
    department_name: "Creative",
    department_id: "166",
    skills: [
        {
            name: "LEADERSHIP",
            level: 3
        },
        {
            name: "PLANNING",
            level: 2
        },
        {
            name: "RIDING BIKES",
            level: 1
        },
        {
            name: "SEM",
            level: 3
},
{
    people_id: "302",
    first_name: "Aallan",
    last_name: "Armstrong",
    job_title: "Creative Director",
    avatar_file: "avatar-3021372114097",
    department_name: "Creative",
    department_id: "166",
    skills: [ ]
},
}
```

Get Person
----------

Return a specific person identified by the people id.

    `GET /people/1` will return the specific person with the id 1.
    
A sample response:

```
{
    people_id: "1",
    first_name: "Rachel",
    last_name: "Hammond",
    job_title: "Designer",
    avatar_file: "avatar-1",
    department_name: "Creative",
    department_id: "2",
    skills: "css:3|Flash:1|Photoshop:2|design:2"
}
```

Add Person
-------------

Add a new person within your existing account.

    `POST /people`
  
```
{
    first_name: "Rachel",
    last_name: "Hammond",
    job_title: "Designer",
    email: "rachel.hammond@float.com"
}
```

A successful addition will return a `201 Created` response.

Update Person
-------------

Update an existing person within your account.

    `PUT /people/1` will update the person with the id 1.

```
{
    first_name: "New First Name",
    last_name: "New Last Name",
    email: "newfirstname.newlastname@float.com"
}
```
  
Move to Reserve or Return to Active Person
------------------------------------------

This will either move a person to the reserve or return them to active.

    `PUT /people/1` will move the person to the reserve with the id 1.
    
```
{
  reserve: "true"
}
```

Change true to false to return the person from the reserve to active.

Delete Person
-------------

This will delete a specific person.

    `DELETE /people/1` will delete the person with the id 1.
    
On success this will return a `204 No Content` response.
