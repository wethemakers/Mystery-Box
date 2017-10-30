########################
KON-TIKI LABS PLATFORM 
########################

This document is intended to get you started with your bot content using the KTL platform APIs.
Check the document below to find out how your bot developers can retrieve the platform ‘flakes’, and perform all the necessary CRUD actions with our simple to use APIs.

===============================
**User : Get the User Details**
===============================

-	**User login**
	
	*Generate access token*

	Get your ‘Access Token’ by providing your platform credentials. Access tokens are required to access data or make changes to your platform data via the APIs.
	An example of the request and response:

	*Request* ::
			
			-------------------------------------------------------------
			| URL    : http://app.kontikilabs.com:3000/api/users/login  |
			-------------------------------------------------------------
			| HEADER : Content-Type:application/json                    |
			-------------------------------------------------------------
			| METHOD : ``POST``                                         |
			-------------------------------------------------------------

	*Data* ::
			
			
			{"email":"<your_email_id>", "password":"<your_password>", "source":"platform"}

	*Response* ::
			
			
			  STATUS CODE : 200 
				{
				  "id": "<ACCESS_TOKEN>",
				  "created": "2017-08-23T06:28:45.142Z",
				  "userId": "<USER_ID>",
				  "userDetail": {
				    "organisation_id": "<ORGANISATION_ID>",
				    "role": "<USER_ROLE_ID>",
				    "username": "<USER_NAME>",
				    "email": "<EMAIL_ID>",
				    "emailVerified": true,
				    "id": "<USER_ID>",
				    "created": "2017-08-21T06:31:57.547Z",
				    "modified": "2017-08-21T06:32:13.938Z"
				  }
				}

	If the data is invalid, you will get the following response ::


			 STATUS CODE : 401 
			 	{
			 	  "error": {
				    "statusCode": 401,
				    "name": "Error",
				    "message": "login failed",
				    "code": "LOGIN_FAILED"
				  }
			 	}

 The following user roles can be used to determine permissions assigned to the user

 +------------+-----------------------------------------+
 |            |                                         |
 | Role       | Description                             |
 |            |                                         |
 +============+=========================================+
 | customer   | The bot users                           |
 +------------+-----------------------------------------+
 | superadmin | User who owns the organisation account  |
 +------------+-----------------------------------------+

-	**Update user**

	The update API allows for updating user details by filling in the desired value in the input JSON. Below is an example of the request and response:

	*Request* ::
			
			-------------------------------------------------------------
			| URL    : http://app.kontikilabs.com:3000/api/users/login  |
			-------------------------------------------------------------
			| HEADER : Content-Type:application/json                    |
			-------------------------------------------------------------
			| METHOD : ``POST``                                         |
			-------------------------------------------------------------


===================================================
**Organisation : Get what your organisation holds**
===================================================




