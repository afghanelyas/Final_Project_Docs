
# API
Sabaq.af is a platform designed to provide users with educational resources and services. To make the most of what Sabaq.af has to offer, users are required to follow a specific process, including user registration, identity verification, profile creation, and the use of API tokens in their interactions with the platform. This document outlines the steps a user needs to take to access the features and content provided by Sabaq.af.

**I. User Registration:**

Access the Website: Visit https://www.sabaq.af.
Sign Up: Click "Sign Up" and provide:
Username
Email address
Password
Submit Registration: Click "Submit" to create your Sabaq.af account.

**II. Identity Verification:**

Verification Email: After registration, check your email for a verification message from Sabaq.af.
Verify Your Email: Click the link in the email to activate your account for security.

**III. Navigating to Your Profile:**

Log In: Return to the website, log in using your username and password.
Access Your Profile: Click your username or profile picture in the top-right corner.

**IV. Creating and Using API Tokens:**

Generate API Token: On your profile page, create a unique API token.
Copy the Token: Copy the generated token to your clipboard.
Attach Token to Requests: When using Sabaq.af's API, attach the token according to the API documentation for authentication.
## Authentication
>{notice} To be updated.

## Class API
**View**
To get list of all classes of authenticated users.
```php
GET /classes
```

The success response looks like:

```php
{
    "data": [
        {
            "id": 1,
            "name": "Class Name",
            "grade": 8,
            "student_count": 0,
            "year": {
                "name": 1402
            },
            "school": {
                "name": "School Name"
            },
            "subjects": [
                {
                    "name": "Subject Name",
                    "en_name": "Subject english name",
                    "pa_name": "Subject Pushto name",
                    "customSubject": false
                },
                ...
            ]
 
        },
        ...
    ]
}
```

**Store**

To create a new issue for project {projectId}:
```php
POST api/projects/{projectId}/issues
```

The above action requires the following data that should be included.

```php
'title'          => 'required|string|max:255|min:3',
'description'    => 'string|max:255',
'suggestion'     => 'required|string|max:255',
'occurrenceDate' => 'required_if:subtaskId,==,""',
'subtaskId'      => 'required_if:occurrenceDate,==,""|numeric',
'priority'       => 'required|numeric',
'timeToSolve'    => 'required|numeric',
'userId'         => 'required|numeric',
'attachments'    => 'nullable'
```

The success response would looks like:
```php
{
        "data": [
            {
                "id": 10,
                "title": "New Isue",
                "description": "Some comment are here.",
                "suggestion": "Some suggestions are here.",
                "impactArea": "Schedule",
                "impactAreaId": 1,
                "status": "Opened",
                "statusId": 1,
                "priorityId": 2,
                "priority": "Normal",
                "timeToSolve": 21,
                "notifyDate": "1398-03-30",
                "occurrenceDate": "1398-03-30",
                "openDate": "1398-03-30",
                "resolvedDate": "",
                "retiredDate": "",
                "resolvedNote": null,
                "retiredNote": null,
                "subtaskId": null,
                "subtaskName": null,
                "projectId": 240,
                "userId": 1,
                "user": "Admin",
                "attachments": [],
                "wasRisk": 0,
                "createdAt": "1398-03-30",
                "type": "issue"
            }
        ]
    }
```

**Update**
To update the issue {id} for project {projectId}.

```php
PUT api/projects/{projectId}/issues/{id}
```
The action payload validation is just like the store method.

The success response would looks like:
```php
{
    "data": [
        {
            "id": 9,
            "title": "Updated title",
            "description": "Some comment are here.",
            "suggestion": "Some suggestions are here.",
            "impactArea": "Schedule",
            "impactAreaId": 1,
            "status": "Opened",
            "statusId": 1,
            "priorityId": 2,
            "priority": "Normal",
            "timeToSolve": 21,
            "notifyDate": "1398-03-30",
            "occurrenceDate": "1398-03-30",
            "openDate": "1398-03-30",
            "resolvedDate": "",
            "retiredDate": "",
            "resolvedNote": null,
            "retiredNote": null,
            "subtaskId": null,
            "subtaskName": null,
            "projectId": 240,
            "userId": 1,
            "user": "Admin",
            "attachments": [],
            "wasRisk": 0,
            "createdAt": "1398-03-30",
            "type": "issue"
        }
    ]
}
```

**Delete**
To delete the issues {id} for project {projectId}.

```php
Delete api/projects/{projectId}/issues/{id}
```

It return the deleted risk.
```php
{
    "data": [
        {
            "id": 1,
            "name": "Class Name",
            "grade": 8,
            "student_count": 0,
            "year": {
                "name": 1402
            },
            "school": {
                "name": "School Name"
            },
            "subjects": [
                {
                    "name": "Subject Name",
                    "en_name": "Subject english name",
                    "pa_name": "Subject Pushto name",
                    "customSubject": false
                },
                ...
            ]
 
        },
        ...
    ]
}
```



## Student API
This section contains the endpoints related to managing student information.

**Index**
Retrieve a list of students in a specific class.

Request
```php
GET /classes/{classRoom}/students
```

Response
The success response looks like:
```php
{
"data": [
    {
        "id": 1,
        "name": "John Doe",
        "father_name": "James Doe",
        "grand_father_name": "Robert Doe",
        "nid_number": "123456789",
        "base_number": 123456789
    },
...
 
    ]
}
```

**Show**
Retrieve detailed information about a specific student in a class.

Request:
```php
POST /classes/{classRoom}/students/{student}
```
Response:
```php
{
    "id": 1,
    "name": "Jane Smith",
    "father_name": "David Smith",
    "grand_father_name": "Michael Smith",
    "nid_number": "987654321",
    "base_number": 123456789
}
```


**Store**
Add a new student to a specific class.

Request:
```php
POST /classes/{classRoom}/students
```
Response:
```php
{
    'name' => 'new name',
    'father_name' => 'new father name',
    'grand_father_name' => 'new grand father name',
    'nid_number' => new id,
    'base_number' => new base_number,
}
```


**Update**
Update information for an existing student in a class.

Request:
```php
PUT /classes/{classRoom}/students/{student}
```

Response:
```php
{
    "name": "update name",
    "father_name": "update father name",
    "grand_father_name": "update grand father name",
    "nid_number": "update nid number",
    "base_number": "update base number"
}
```

**Delete**
Remove a student from a specific class.

Request
```php
DELETE /classes/{classRoom}/student/{student}
```

Reaponse
```php
No content
```

## Subject API
This documentation provides an overview of the API endpoints and actions for managing subjects within the API system.

**Index**
This endpoint allows you to retrieve the subjects associated with a specific class.

Request:
```php
GET /api/classes/{classRoom}/subjects
```

Request Prameters
>{notice} {classRoom}: The ID of the class for which you want to retrieve subjects.

Response:
```php
{
    "data": [
        {
            "id": 1,
            "name": "Math",
            "en_name": "Math",
            "pa_name": "Math",
            "customSubject": false
        },
    ]
}
```

**Store**
This endpoint allows you to create a new subject and associate it with a class.

Request:
```php
POST /api/classes/{classRoom}/subjects
```

Request Prameters:
>{notice} {classRoom}: The ID of the class to which the subject will be added.
>{notice} name: The name of the subject.
>{notice} en_name: The English name of the subject.
>{notice} pa_name: The Pashto name of the subject.

Example Request:
```php
{
    "name": "Science",
    "en_name": "Science",
    "pa_name": "Science"
}
```

Response:
```php
{
    "data": {
        "id": 2,
        "name": "Science",
        "en_name": "Science",
        "pa_name": "Science",
        "customSubject": true
    }
}
```

Delete
This endpoint allows you to delete a subject from a class.

Request:
```php
DELETE /api/classes/{classRoom}/subjects/{subject}
```

Request Parameters
>{notice} {classRoom}: The ID of the class from which the subject will be deleted.
>{notice} {subject}: The ID of the subject to be deleted.

Response

```php
No Content
```

## Attendance API
This documentation provides an overview of the API endpoints and resources available for managing attendance data in a school management system.

**Store**
Create a new attendance record for a student.

Request:
```php
POST /attendance
```

Request Prameters:
```php
student_id (integer, required): The ID of the student.
present (boolean): Whether the student is present (default: true).
absents (integer): Number of absents (default: 0).
sickness (integer): Number of sickness-related absences (default: 0).
leave (integer): Number of leave-related absences (default: 0).
```

Response:
Returns the created attendance record in JSON format.

>{notice} Success (Http 201 created)

If validation fails, an error response with details will be returned.

>{notice} Error (HTTP 422 Unprocessable Entity)


**Update**
Update an existing attendance record for a student.

Request:
```php
PUT /attendances/{attendance}
```

Request Parameters
>{notice}  attendance (integer, required): The ID of the attendance record to be updated.

Example Request:
```php
{
    "student_id": 1,
    "present": true,
    "absents": 2,
    "sickness": 1,
    "leave": 0
}
```

Response:
```php
{
    "student_id": 1,
    "present": true,
    "absents": 2,
    "sickness": 1,
    "leave": 0
}
```