API Documentation
This documentation provides information on setting up, running, and testing the API, including details on authorization and available routes.

Setting Up and Running the API
Download Files from Git Repo:

Clone the repository to your local machine using the following command:
bash
Copy code
git clone https://github.com/your-username/your-repo.git
Navigate to the project directory.
Install Dependencies:

Run the following command to install all dependencies:
Copy code
npm install
Start the API:

Run the following command to start the API:
Copy code
node index.js
Authorization
The API requires authorization to access protected endpoints. Use the provided token in the header as follows:

Key: authorization
Value: Bearer your-token-here
Ensure that you replace your-token-here with the actual token provided during authentication.

Testing the API
Users Routes
1. Sign Up (POST)
URL: localhost:3000/users/signup/

Input Format:

json
Copy code
{
    "name": "exampleUser",
    "email": "example@example.com",
    "password": "password123"
}
Response:

Success: "User Signed Up Successfully."
Failure: "User with this email already exists."
2. Login (POST)
URL: localhost:3000/users/login/

Input Format:

json
Copy code
{
    "email": "example@example.com",
    "password": "password123"
}
Response:

Success: "Authentication successful." (Includes JWT token)
Failure: "Authentication failed."
Tasks Routes
1. Create a New Task (POST)
URL: localhost:3000/tasks/

Input Format:

json
Copy code
{
    "title": "Example Task",
    "description": "Task details here",
    "assigned_user": "exampleUser",
    "due_date": "2023-12-11",
    "completionStatus": false,
    "completionTime": "2023-11-26"
}
2. Get All Tasks (GET)
URL: localhost:3000/tasks/

Response Format:

json
Copy code
{
    "Tasks": [
        {
            "_id": "exampleTaskId1",
            "title": "Example Task",
            "description": "Task details here",
            "assigned_user": "exampleUser",
            "due_date": "2023-12-11",
            "completionStatus": false,
            "completionTime": "2023-11-26T05:14:23.900Z",
            "createdAt": "2023-11-26T05:14:23.905Z",
            "updatedAt": "2023-11-26T05:16:11.359Z",
            "__v": 0
        },
        // Additional tasks...
    ]
}
3. Get Task by ID (GET)
URL: localhost:3000/tasks/:Id/

Response Format:

json
Copy code
{
    "Task": {
        "_id": "exampleTaskId1",
        "title": "Example Task",
        "description": "Task details here",
        "assigned_user": "exampleUser",
        "due_date": "2023-12-11",
        "completionStatus": false,
        "completionTime": "2023-11-26T05:14:23.900Z",
        "createdAt": "2023-11-26T05:14:23.905Z",
        "updatedAt": "2023-11-26T05:16:11.359Z",
        "__v": 0
    }
}
4. Update a Task (PATCH)
URL: localhost:3000/tasks/:Id/

Input Format:

json
Copy code
{
    "due_date": "2023-12-11",
    "completionStatus": false
}
5. Delete a Task (DELETE)
URL: localhost:3000/tasks/:Id/
6. Get Tasks Completed within Last "N" Days (GET)
URL: localhost:3000/tasks/analytics/completed-last-days/:numberOfDays

Response Format:

json
Copy code
{
    "count": 5
}
Replace :Id and :numberOfDays with the actual task ID and the desired number of days, respectively.









 




