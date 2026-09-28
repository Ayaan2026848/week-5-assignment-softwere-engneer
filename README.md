A) User Manual Procedure: Setting Up a GitHub Repository and Making a First Commit

Prerequisites

Before starting, make sure you have:

A computer with internet access.

A web browser such as Google Chrome, Firefox, or Microsoft Edge.

A GitHub account.

Your GitHub username and password.

A file that you want to upload to the repository.

Basic knowledge of using a computer and web browser.

Procedure

1. Open GitHub in your web browser.

Expected result: The GitHub website opens successfully.

2. Sign in to your GitHub account.

Expected result: Your GitHub account homepage appears.

3. Select the + button in the upper-right corner of the GitHub page.

Expected result: A menu with several options appears.

4. Select New repository from the menu.

Expected result: The Create a new repository page opens.

5. Enter a name for your repository in the Repository name field.

Expected result: The repository name appears in the repository name field.

6. Select Public as the repository visibility.

Expected result: The Public option is selected.

7. Select Create repository.

Expected result: GitHub creates the new repository and opens the repository page.

8. Select Add file.

Expected result: A menu with file-related options appears.

9. Select Upload files.

Expected result: The file upload page opens.

10. Select the file you want to upload.

Expected result: The selected file appears in the upload area.

11. Select Commit changes.

Expected result: GitHub saves the file and creates the first commit.

12. Open the main page of the repository.

Expected result: The uploaded file appears in the repository file list, and the latest commit is displayed.

Screenshot Description

A screenshot should show the main page of the newly created GitHub repository after the first commit. The screenshot should display the repository name, the uploaded file, and the latest commit message.

Troubleshooting

Problem: The Commit changes button is not available.

Solution: Make sure that you have selected or uploaded a file first. After a file is ready to be saved, GitHub displays the option to commit the changes.


B API Reference Entry Create a New Task

Create a Task

HTTP Method: POST

Endpoint: /api/v1/projects/{projectId}/tasks

Description

This endpoint allows an authenticated user to create a new task inside a project management application. The task includes a title, an optional description, an assignee, a due date, and a priority level.

Path Parameters

Parameter: projectId

Data Type: string

Required: Yes

Description: The unique ID of the project where the new task will be created.

Query Parameters

This endpoint does not require any query parameters.

Request Body Parameters

Parameter: title

Data Type: string

Required: Yes

Description: The name or title of the task.

Parameter: description

Data Type: string

Required: No

Description: Additional information about the task.

Parameter: assigneeId

Data Type: string

Required: Yes

Description: The unique ID of the user assigned to the task.

Parameter: dueDate

Data Type: string

Required: Yes

Description: The date when the task is due, using the YYYY-MM-DD format.

Parameter: priority

Data Type: string

Required: Yes

Description: The priority level of the task. Allowed values are low, medium, or high.

Request Headers

Authorization

Required: Yes

Description: Contains the authentication token using the Bearer scheme.

Content-Type

Required: Yes

Description: Specifies that the request body is formatted as JSON.

Example Request

POST /api/v1/projects/proj-102/tasks

Authorization: Bearer eyJhbGciOi...

Content-Type: application/json

Request Body

{
"title": "Complete project documentation",
"description": "Write and review the technical documentation.",
"assigneeId": "user-458",
"dueDate": "2026-10-15",
"priority": "high"
}

HTTP Response Codes

201 Created: The task was successfully created.

400 Bad Request: The request contains missing or invalid information.

401 Unauthorized: The authentication token is missing or invalid.

403 Forbidden: The authenticated user does not have permission to create a task in the project.

404 Not Found: The specified project or assignee does not exist.

409 Conflict: The request conflicts with an existing resource or project rule.

422 Unprocessable Entity: The request is correctly formatted, but one or more values fail validation.

500 Internal Server Error: An unexpected error occurred on the server.

Successful Response

Status Code: 201 Created

The server returns the newly created task.

{
"id": "task-7834",
"projectId": "proj-102",
"title": "Complete project documentation",
"description": "Write and review the technical documentation.",
"assigneeId": "user-458",
"dueDate": "2026-10-15",
"priority": "high",
"status": "todo",
"createdAt": "2026-09-28T12:30:00Z"
}

Response Fields

id: The unique ID of the newly created task. Data type: string.

projectId: The ID of the project containing the task. Data type: string.

title: The title of the task. Data type: string.

description: Additional information about the task. Data type: string.

assigneeId: The ID of the user assigned to the task. Data type: string.

dueDate: The task deadline in YYYY-MM-DD format. Data type: string.

priority: The task priority: low, medium, or high. Data type: string.

status: The current status of the task. A new task starts with todo. Data type: string.

createdAt: The date and time when the task was created, using ISO 8601 format. Data type: string.
