Float API
=========

Welcome to the Float API. Use this API to integrate with your favorite third party applications and share, create and update your Float data including: 

* [People](https://github.com/floatschedule/api/blob/master/Sections/people.md)
* [Projects](https://github.com/floatschedule/api/blob/master/Sections/projects.md)
* [Tasks](https://github.com/floatschedule/api/blob/master/Sections/tasks.md)
* [Holidays](https://github.com/floatschedule/api/blob/master/Sections/holidays.md)

See http://www.floatschedule.com for more info about Float.

Now to the important stuff:

Getting Setup
-------------

This is a REST-style API that uses HTTP POST data and JSON for all responses. It uses OAuth 2 for authentication.

All URLs start with `https://app.floatschedule.com/api/f1/`

'f1' represents the version number. If we update the version, we'll update this number and continue to support those previous. 

If you were to make a request for all people on your account it would look like this:

`https://app.floatschedule.com/api/f1/people`

Content-Type must be defined in the header of requests that contain data:

`Content-Type: application/x-www-form-urlencoded`

The Accept header should be set to application/json since that is the supported return format of the API.

`Accept: application/json`

Identify Yourself
-----------------

We like to know who you are so we can contact you if there's any issues or opportunities. Please include a 'User-Agent' header with the name of your application and a contact email. Here's a sample:

`User-Agent: Yaron's People Import Integration (yaron@pixelpaddock.com)`
    

Request Limits
--------------

You can make up to 6 requests a second from the same account. Following this you will receive a '429 Error: too many requests by this user'. You will need to wait 30 minutes before attempting another request.


Other Errors
------------

Other errors you may see will start with 5xx, e.g. 502 Bad Gateway. Please hold and try your request again later.


API Improvements
----------------

We're tracking all issues and feature requests for the API via the GitHub issues. You can also fork these docs and send a pull request with updates.

For any other requests you can contact us at support@floatschedule.com

