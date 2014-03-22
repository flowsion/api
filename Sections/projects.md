Float Projects
==============


Get Projects
------------

	GET /projects
will return all active projects.

    
A sample response:
```json
{
	"projects": [
	{
            "project_id": "223",
            "project_name": "iPhone App",
            "description": "Marquee project for us. Need to consider a contractor with app dev skills.",
            "vacation": "0",
            "color": "9e7fba",
            "client_id": "212",
            "client_name": "Violet City",
            "tags": [
		        	{        
                        "IPHONE APP",
                        "MEDIUM"
                	}
		       ],
            "project_managers": [
                    {
                        "account_id": "135",
                        "name": "Glenn Baron",
                        "email": "float@pixelpaddock.com"
                  	}
		       ]
	},
	{		       
            "project_id": "224",
            "project_name": "Microsite",
            "description": "For an existing client.",	
		...
}
```

<h3>Archived vs Active Projects</h3>

To access projects that are **archived** add the query string: `&active=0`.

Use: `&active=1` to view all **archived** projects.

Get Project
-----------

Return a specific project identified by the project id.

	GET /projects/123
will return the specific person with the id 123.
    
A sample response:

```json
{
    "project_id": "223",
    "project_name": "iPhone App",
    "description": "Marquee project for us. Need to consider a contractor with app dev skills.",
    "vacation": "0",
    "color": "9e7fba",
    "client_id": "212"
    "client_name": "Violet City",
        "tags": [
	        {        
                "IPHONE APP",
                "MEDIUM"
        	}
	        ],
        "project_managers": [
            {
                "account_id": "135",
                "name": "Glenn Baron",
                "email": "float@pixelpaddock.com"
          	}
	    ]
}
```

Add Project
-------------

Add a new project within your existing account.

    POST /projects
POST requests must be _application/x-www-form-urlencoded_ in name/value pairs. Data must also be URL encoded as appropriate.

Sample request:

	project_name=Microsite&description=Important_job_for_client.&color=9e7fba

Valid fields with example values:

    project_name=Microsite
    description=Important job for client.
    color=9e7fba
    client_id=2
    tags=Microsite,Medium

A successful create record will return a `201 Created` response status with the new id:

```json
{
	"project_id":"4323"
}
```

Update Project
--------------

Update an existing person within your account.

    PUT /projects/123
will update the project with the id 123.
PUT requests must be _application/x-www-form-urlencoded_ in name/value pairs. Data must also be URL encoded as appropriate.

	Update format and field values are the same as create, see above.

A successful update will return a `200 Ok` response status.

Delete Project
--------------

Delete a specific project.

    DELETE /projects/123
will delete the project with the id 123. _Warning: deletes can not be undone and data can not be recovered, please use with care._
    
A successful delete will return a `200 Ok` response status.
