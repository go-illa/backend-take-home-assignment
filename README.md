Take-home assignment
ILLA
Creating the back-end of a Transportation Management System
Overview
You will be building the first API endpoints of a transportation management system. This API should be compliant with the JSON:API specification and should use JWT for authentication.
The API should have endpoints for signing in and signing up, listing trucks, assigning a truck to a driver, and listing all trucks that the current driver is assigned to.
Additionally, the application should periodically fetch trucks from a remote API and store them locally.
Technical Requirements
Use Ruby on Rails and PostgreSQL.
Use Minitest or Rspec for your tests.
The API should be JSONAPI-compliant.
The API should support authentication with JWT.
Refrain from using baked solutions like Devise::JWT or Knock; we would love to see you implementing it at a lower level (using bcrypt and the JWT gem, for example)
Functional Requirements
The API should have endpoints to:
Create a new driver account with the given email and password.
Authenticate a driver with the given email and password and return a JWT token.
Return a list of all trucks (including truck name and truck type).
Assign the current driver to a truck with a given truck ID.
Return a list of all trucks that the current driver is assigned to (including the names of the trucks that the driver is assigned to and the respective assignment dates).
A driver may get assigned to multiple trucks simultaneously, and a truck may have many drivers at the same time.
Finally, the application should also have a Sidekiq worker that periodically fetches data from a remote API and updates the local database with new trucks. Make sure to schedule it to run periodically (e.g. once a day).
The External API
This is the endpoint you'll be using to fetch the trucks:
https://api-task-bfrm.onrender.com/api/v1/trucks

Important note: the External API is using pagination, you can inspect the HTTP headers of the response, and you will see the following headers: current-page, page-items, total-count, and total-pages, you should be able to use these headers to paginate through records.
We’re using the Pagy gem for pagination, check the documentation for HTTP headers if you want more details. 
The API key is illa-trucks-2023, which should be passed in as an API_KEY header.

Evaluation Criteria
We will evaluate your submission based on the following criteria:
Functionality: Does your API meet the functional requirements described above?
Code Quality: Is your code well-organized, documented, and easy to understand?
Testing: Is the application well-tested? What kinds of tests did you use?
Architecture: Is your code structured in a way that is scalable and maintainable? Did you apply SOLID principles?
Communication: Have you provided clear instructions for running your code, and have you communicated effectively with us throughout the process?
🌟 Deliverables
Please submit your deliverables to the hiring manager via email. Ahmad Amin (ahmed.amin@illa.com.eg), and CC Ahmed Abdelhamid our senior backend engineer (ahmed.abdelhamid@illa.com.eg)

Deliverables should include:
A demo video (recorded using Loom or similar tools) showcasing your solution as well as the code behind it. Please ensure your microphone is on.
A zipped Git repository including all necessary instructions for running the code locally. Your code should be well-organized, and documented, and includes tests. Please be sure to include the .git folder in your ZIP file so that we can view your commit history. Do NOT upload your repository to GitHub.


Closing Comments
We look forward to seeing your submission. Write your cleanest code and don't be afraid of showing your opinion through it. We would like to see how you organize your code and, more generally, what is your approach to writing software. If you have any questions or concerns, please don't hesitate to reach out to us. Have fun!
