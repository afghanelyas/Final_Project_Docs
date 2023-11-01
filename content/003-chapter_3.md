# Research Design and Methodology
Agile estimation techniques are collaborative. All appropriate people are
included in the process. For example the whole team participates in esti-
mating effort of Product Backlog Items. Collaborative techniques are also
designed so that it is impossible to blame someone for an incorrect estimate:
there is no way to trace who estimated what. Agile estimation techniques
are designed to be fast (than traditional techniques) and deliberately trade
off accuracy. We are not trying to learn to predict the future or get better at
estimation. Instead, we recognize that estimation is a non-value added ac-
tivity and minimize it as much as possible. Most Agile estimation techniques
use relative units. This means that we dont try to estimate dollars or days
directly. Instead, we use points or even qualitative labels and simply com-
pare the items we are estimating to each other. This takes advantage of the
human capacity to compare things to each other and avoids our difficulty in
comparing something to an abstract concept (such as dollars or days). One
of the key advantages of adopting an agile workflow is the ability of the team
to estimate new work effectively. Over time, as team members encounter
new user stories, they should develop an increasingly accurate sense of how
theyre going to approach stories and how much effort each user story will
take to complete. Once a team has been working together for a while, their
ability to estimate new stories becomes much better. Teams with a history
of past successes and failures can compare their velocity against point es-
timates that everyone can agree to, and as a result they can predict with
reasonable accuracy how difficult it will be for them to complete a new story.
But teams new to agile sometimes have difficulty figuring out how to estimate
stories effectively. For some, the abstract and team-specific concept of points
is difficult to grasp. For others, the soft relationship between point value
and actual time spent working on a story can be distracting. Until a team
has been working together for a while, attempts to generate accurate point
estimates for new stories may feel awkward and loose. Here is a estimation
techniques for agile teams that can ease the transition through this phase.
This technique get everyone engaged in productive point estimation from the
start, regardless of their level of experience with agile methods. Estimating
the cost of an IS development project is one of the most crucial tasks for
project managers [6](Keung et al., 2004)


# API
An API, or Application Programming Interface, is like a set of rules that helps different software applications have a conversation. It tells them how to ask for things and share information.
Key Parts of an API:
Methods or Endpoints: Think of these as actions. They tell the apps what to do, like getting data, sending data, or doing a specific task.
Request Format: When you talk to an API, you make a request. This is like telling it what you want to do. You might also give it your ID to prove who you are.
Response Format: The API answers back with information or says, "Yep, I did it!" The answer comes in a specific way, like a language the apps understand, such as JSON or XML.
Data Exchange: APIs let apps share all sorts of stuff - words, numbers, pictures, files, or anything they need to talk about. It's like the way they pass notes to each other.

### How dose API work
* Request: You start by asking the API to do something for you. You tell it what you want, and sometimes, you give it extra information.
* Processing: The API gets to work, like a helpful assistant. It might search for information, do some calculations, or talk to other services.
* Response: When it's done, the API sends you a message. This message contains the answers to your request or the information you wanted.
* Integration: Now, your own program can use this information from the API to do its own job or show the data to people. It's like using the results of a task done by your assistant to complete your work.

### Authentication
>{notice} To be updated.

### Class API
*View*
*Store*
*Update*
*Delete*

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
To get the list of project issues via pagination

```php
GET api/projects/{projectId}/paginated-issues
```
The success response would looks like:

```php
{
    "data": [
        {
            "id": 9,
            "title": "Title",
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
    ],
    "meta": {
        "pagination": {
            "total": 1,
            "count": 1,
            "per_page": 6,
            "current_page": 1,
            "total_pages": 1,
            "links": []
        }
    }
}
```

To get all issues:
```php
GET api/issues
```

It returns the risks stored in system.

```php
{
    "data": [
        {
            "id": 9,
            "title": "Title",
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

**Drop Down Values**
To get the drop down values such as impact area, time to notify and source :

```php
GET /ap/issues/dropdowns
```
The success response would look like:

```php
{
    "impactAreas": [
        {
            "value": "1",
            "displayValue": "Schedule"
        },
        {
            "value": "2",
            "displayValue": "Scope"
        },
        {
            "value": "3",
            "displayValue": "Budget"
        },
        {
            "value": "4",
            "displayValue": "Quality"
        }
    ],
    "status": [
        {
            "value": "1",
            "displayValue": "Open"
        },
        {
            "value": "2",
            "displayValue": "Resolved"
        },
        {
            "value": "3",
            "displayValue": "Retired"
        }
    ],
    "priority": [
        {
            "value": "1",
            "displayValue": "Low"
        },
        {
            "value": "2",
            "displayValue": "Normal"
        },
        {
            "value": "3",
            "displayValue": "High"
        }
    ]
}
```

Review
To review and update the status and other staff of issues {riskId}:

POST api/projects/{projectId}/issues/{id}/review

The required data and validations are same as store method.

The success response looks like:

{
    "data": [
        {
            "id": 9,
            "title": "Title",
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


**Filter**
To filter the risks for the project {projectId}

```php
POST api/projects/{projectId}/issues/filter
```

The action post data should looks like:

```php
[
    {
        column: "Id"
        id: "698"
        operator: "="
        readValue: "202"
        value: "202"
    },
    ...
]
```

The above query will returns the project's {projectId} issues which id is 202.

To filter action data does accept multiple filter:

```php
[
    {
        column: "Status"
        id: "557"
        operator: "="
        readValue: "Open"
        value: "1"
    },
    {
        column: "Id"
        id: "761"
        operator: "="
        readValue: "202"
        value: "202"
    },
    ...
]
```

Now the filter action will return the risks which their status is open and the id is 202.

To know the values available for property column of payload property:

```php
GET api/issues/columns
```

It return the columns that can be filtered by
```php
[
    "Id",
    "Impact Area",
    "Status",
    "Responsible Person"
]
```

The operation property of payload can be the following
```php
'='     // To check the equality
'like'  // To check the like query
'!='    // To check the not equality
'>'     // To check the grather than
'<'     // To check the less than
'>='    // To check the grather than or equal to
'<='    // To check the less than or equal to
```

finally the response of filter looks like:

```php
{
    "data": [
        {
            "id": 9,
            "title": "Title",
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

**Student API**
This section contains the endpoints related to managing student information.

*Index*
*Show*
*Store*
*Update*
*Delete*

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
        "nid_number": 123456789,
        "base_number": STU123456
    },
    {
        "id": 2,
        "name": "Jane Smith",
        "father_name": "David Smith",
        "grand_father_name": "Michael Smith",
        "nid_number": 987654321,
        "base_number": STU987654
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
    "nid_number": 987654321,
    "base_number": STU987654
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

**Subject API**
This documentation provides an overview of the API endpoints and actions for managing subjects within the API system.

*Index*
*Store*
*Delete*

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

**Attendance**
This documentation provides an overview of the API endpoints and resources available for managing attendance data in a school management system.

*Store*
*Update*

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