Float API
=========

Welcome to the Float API. Use this API to integrate with your favorite third party and in-house applications to share, create and update your Float data including: 

* [People](https://github.com/floatschedule/api/blob/master/Sections/people.md)
* [Projects](https://github.com/floatschedule/api/blob/master/Sections/projects.md)
* [Tasks](https://github.com/floatschedule/api/blob/master/Sections/tasks.md)
* [Holidays and Milestones](https://github.com/floatschedule/api/blob/master/Sections/holidays.md)

(Hint: Press `t` to enable the file finder.)

Visit https://www.float.com to learn more about Float.

Now onto the important stuff:

Getting Set Up
--------------

This is a [RESTful](http://en.wikipedia.org/wiki/Representational_state_transfer) API that uses HTTP requests and returns JSON for all responses. It uses an authentication token in the header for to make requests on behalf of a Float user. See below for connection examples.

All URLs start with the root URL: `https://api.float.com/api/v1/`

'v1' represents the version number. If we update the version, we'll update this number and continue to support those previous. 

If you were to make a request for all people on your account it would look like this:

`https://api.float.com/api/v1/people`

Content-Type must be defined in the header of requests that contain data. We currently support submissions as form data in name/value pairs. Set the Content-Type header to "application/x-www-form-urlencoded" like this:

`Content-Type: application/x-www-form-urlencoded`

The Accept header should be set to "application/json", since that is the supported return format of the API. (All results will be in JSON format.) That header should look like this:

`Accept: application/json`

Please note that all requests to the Float API must be made over HTTPS. 

Authentication
--------------

When making a call to our API endpoints, you must supply an Authorization header.

Add the following HTTP header to your request: 

`Authorization: Bearer FLOAT_ACCESS_TOKEN` 

where FLOAT_ACCESS_TOKEN is the api token you obtained from your Float Account & Billing page (currently in beta).

We use the OAuth 2.0 protocol for API authentication, but only a subset of the specification is exposed. The token you receive on our web site is pre-authorized by being logged into the admin screen -- basically you pick it up from the point where you are working with an access token to make authorized requests for Float resources. 

The API token you receive on our site is a Bearer token, which will grant access to Float API resources on behalf of a specific user -- in this case, the account owner. This token should be considered as sensitive as passwords and must not be shared or distributed to untrusted parties.

(If you are interested in using alternative OAuth 2.0 connection methods or have questions about connecting to specific applications, please contact us at support@float.com)


Identify Yourself
-----------------

We like to know who you are so we can contact you if there's any issues. Please include a 'User-Agent' header with the name of your application and a contact email. Here's a sample:

`User-Agent: Yaron's People Import Integration (techie@pixelpaddock.com)`
    

Request Limits
--------------

You can make up to 200 requests a minute from the same account. Following this you will receive a '429 Error: too many requests by this user'. You will need to wait a brief period before attempting additional requests.


Other Errors
------------

Other errors you may see will start with 5xx, e.g. 500 Internal Server Error. Please hold and try your request again later. If the error persists please contact us at the email below.


API Improvements
----------------

We're tracking all issues and feature requests for the API via the GitHub issues. You can also fork these docs and send a pull request with updates.

For any other requests you can contact us at support@float.com

