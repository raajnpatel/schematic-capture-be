[![Maintainability](https://api.codeclimate.com/v1/badges/b5735c25bf5c795c770c/maintainability)](https://codeclimate.com/github/Lambda-School-Labs/schematic-capture-be/maintainability) [![Test Coverage](https://api.codeclimate.com/v1/badges/b5735c25bf5c795c770c/test_coverage)](https://codeclimate.com/github/Lambda-School-Labs/schematic-capture-be/test_coverage)

🚫 Note: All lines that start with 🚫 are instructions and should be deleted before this is posted to your portfolio. This is intended to be a guideline. Feel free to add your own flare to it.

🚫 The numbers 1️⃣ through 3️⃣ next to each item represent the week that part of the docs needs to be comepleted by. Make sure to delete the numbers by the end of Labs.

🚫 Each student has a required minimum number of meaningful PRs each week per the rubric. Contributing to docs does NOT count as a PR to meet your weekly requirements.

# API Documentation

#### 1️⃣ Backend delpoyed at [🚫name service here](🚫add URL here) <br>

## 1️⃣ Getting started

To get the server running locally:

🚫 adjust these scripts to match your project

-   Clone this repo
-   **yarn install** to install all required dependencies
-   **yarn server** to start the local server
-   **yarn test** to start server using testing environment

### Backend framework goes here

🚫 Why did you choose this framework?

-   Point One
-   Point Two
-   Point Three
-   Point Four

## 2️⃣ Endpoints

🚫This is a placeholder, replace the endpoints, access controll, and descriptioin to match your project

#### Organization Routes

| Method | Endpoint                | Access Control | Description                                  |
| ------ | ----------------------- | -------------- | -------------------------------------------- |
| GET    | `/organizations/:orgId` | all users      | Returns the information for an organization. |
| PUT    | `/organizatoins/:orgId` | owners         | Modify an existing organization.             |
| DELETE | `/organizations/:orgId` | owners         | Delete an organization.                      |

#### User Routes

| Method | Endpoint              | Access Control      | Description                                         |
| ------ | --------------------- | ------------------- | --------------------------------------------------- |
| POST   | `/api/register`       | all users           | Registers user.                                     |
| POST   | `/api/login`          | registered users    | Logs in a registered user.                          |
| POST   | `/api/forgotPassword` | registered users    | Sends email to provided address for password reset. |
| POST   | `/api/changeEmail`    | authorized users    | Sends email to provided address for email reset.    |
| DELETE | `/api/:userId`        | owners, supervisors |                                                     |

# Data Model

🚫This is just an example. Replace this with your data model

#### 2️⃣ ORGANIZATIONS

---

```
{
  id: UUID
  name: STRING
  industry: STRING
  paid: BOOLEAN
  customer_id: STRING
  subscription_id: STRING
}
```

#### USERS

---

```
{
  id: UUID
  organization_id: UUID foreign key in ORGANIZATIONS table
  first_name: STRING
  last_name: STRING
  role: STRING [ 'owner', 'supervisor', 'employee' ]
  email: STRING
  phone: STRING
  cal_visit: BOOLEAN
  emp_visit: BOOLEAN
  emailpref: BOOLEAN
  phonepref: BOOLEAN
}
```

## 2️⃣ Actions

🚫 This is an example, replace this with the actions that pertain to your backend

`getOrgs()` -> Returns all organizations

`getOrg(orgId)` -> Returns a single organization by ID

`addOrg(org)` -> Returns the created org

`updateOrg(orgId)` -> Update an organization by ID

`deleteOrg(orgId)` -> Delete an organization by ID
<br>
<br>
<br>
`getUsers(orgId)` -> if no param all users

`getUser(userId)` -> Returns a single user by user ID

`addUser(user object)` --> Creates a new user and returns that user. Also creates 7 availabilities defaulted to hours of operation for their organization.

`updateUser(userId, changes object)` -> Updates a single user by ID.

`deleteUser(userId)` -> deletes everything dependent on the user

## 3️⃣ Environment Variables

In order for the app to function correctly, the user must set up their own environment variables.

create a .env file that includes the following:

### Postgres configs for knex

-   DB_ENV=(environment the db is in [ie: development, staging, etc.])
-   DB_HOST=(address or hostname)
-   DB_PORT=(port number database is listening on)
-   DB_USER=(username for database)
-   DB_PASSWORD=(password for database)
-   DB_DATABASE=(name of database)

## Deploying a Postgres database with Docker for testing and/or development

An easy way to get a Postgres database running locally is to run it in a docker container. Follow the steps below in a terminal to get started.

1. `docker pull postgres`

2. `docker run --name container_name -e POSTGRES_USER=username -e POSTGRES_PASSWORD=password -p 5432:5432 -d postgres`

3. Plug in the username and password chosen into the `.env` file (see above) for knex to pick up the correct configs. (The database name will be the same as the username)

### Useful commands:

| Command                                   | Description                                          |
| ----------------------------------------- | ---------------------------------------------------- |
| `docker container stop container_name`    | kill the database container                          |
| `docker container start container_name`   | start the database container                         |
| `docker container restart container_name` | restart the database container                       |
| `docker container rm container_name`      | delete the container (container must not be running) |

## Contributing

When contributing to this repository, please first discuss the change you wish to make via issue, email, or any other method with the owners of this repository before making a change.

Please note we have a [code of conduct](./code_of_conduct.md). Please follow it in all your interactions with the project.

### Issue/Bug Request

**If you are having an issue with the existing project code, please submit a bug report under the following guidelines:**

-   Check first to see if your issue has already been reported.
-   Check to see if the issue has recently been fixed by attempting to reproduce the issue using the latest master branch in the repository.
-   Create a live example of the problem.
-   Submit a detailed bug report including your environment & browser, steps to reproduce the issue, actual and expected outcomes, where you believe the issue is originating from, and any potential solutions you have considered.

### Feature Requests

We would love to hear from you about new features which would improve this app and further the aims of our project. Please provide as much detail and information as possible to show us why you think your new feature should be implemented.

### Pull Requests

If you have developed a patch, bug fix, or new feature that would improve this app, please submit a pull request. It is best to communicate your ideas with the developers first before investing a great deal of time into a pull request to ensure that it will mesh smoothly with the project.

Remember that this project is licensed under the MIT license, and by submitting a pull request, you agree that your work will be, too.

#### Pull Request Guidelines

-   Ensure any install or build dependencies are removed before the end of the layer when doing a build.
-   Update the README.md with details of changes to the interface, including new plist variables, exposed ports, useful file locations and container parameters.
-   Ensure that your code conforms to our existing code conventions and test coverage.
-   Include the relevant issue number, if applicable.
-   You may merge the Pull Request in once you have the sign-off of two other developers, or if you do not have permission to do that, you may request the second reviewer to merge it for you.

### Attribution

These contribution guidelines have been adapted from [this good-Contributing.md-template](https://gist.github.com/PurpleBooth/b24679402957c63ec426).

## Documentation

See [Frontend Documentation](🚫link to your frontend readme here) for details on the fronend of our project.
🚫 Add DS iOS and/or Andriod links here if applicable.
