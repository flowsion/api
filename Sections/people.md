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
    departments: [
        {
            name: "Creative",
            id: "4"
        }
        ],
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
        ],
    email: "abel@pixelpaddock.com",
    description: "This is a description.",
    mobile: "212 444 1221",
    telephone: "333 222 1111",
    im: "abel1"
},
{
    people_id: "302",
    first_name: "Aallan",
    last_name: "Armstrong",
    job_title: "Creative Director",
    avatar_file: "avatar-3021372114097",
    departments: [
        {
            name: "Creative",
            id: "5"
        }
        ],
    skills: [ ],
    email: "aallan@pixelpaddock.com",
    description: "This is a description.",
    mobile: "212 444 1222",
    telephone: "333 222 1123",
    im: "aallaniam"
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
  
People on the Reserve
---------------------

To access people on the reserve add the query string `&active=0`.

Change `&active=1` to view all active people.


Delete Person
-------------

This will delete a specific person.

    `DELETE /people/1` will delete the person with the id 1.
    
On success this will return a `200 Ok` response.
