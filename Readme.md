# GraphQL API for User CRUD Operations

This project implements a GraphQL API for performing CRUD operations on user data. It allows users to create, read and delete user records.

## Folder Structure

```
.
├── models
│   └── user.js
├── schema
│   └── schema.js
├── index.js
├── package.json
└── README.md
```

- **models**: Contains the MongoDB schema definition for the User model.
- **schema**: Contains the GraphQL schema definition.
- **index.js**: Entry point of the application where the server is configured and started.
- **package.json**: Contains project metadata and dependencies.
- **README.md**: This file, providing information about the project.

## Getting Started

### Prerequisites

Before running the application, ensure you have the following installed:

- Node.js
- MongoDB Atlas account (or local MongoDB instance)

### Installation

1. Clone the repository:

   ```bash
   git clone <repository_url>
   ```

2. Install dependencies:

   ```bash
   npm install
   ```

3. Set up MongoDB Atlas:
   - Create a cluster on MongoDB Atlas.
   - Get the connection URI for your cluster.
   - Replace the connection URI in `index.js` with your own MongoDB Atlas connection URI.

## Usage

### Starting the Server

Run the application:

```bash
npm start
```

### GraphQL Playground

Once the server is running, you can access the GraphQL Playground to test the API.

Open your web browser and navigate to:

```
http://localhost:4000/graphql
```

### Testing Endpoints

Open Postman and create a new request.
Enter the URL of the GraphQL endpoint in the URL field.
In the Body tab, select raw and JSON.

#### Read Users

To retrieve a list of all users, send the following GraphQL query (request method get):

```json
{
  "query": "{ users { name age email } }"
}
```

#### Create New User

To create a new user, send the following GraphQL mutation(request method post):

```json
{
  "query": "mutation { addUser(name: \"John\", age: 30, email: \"john@example.com\") { name age email } }"
}
```

#### Delete User

To delete a user, send the following GraphQL mutation(request method post):

```json
{
  "query": "mutation { deleteUser(id: \"userId\") { name age email } }"
}
```

Replace `"userId"` with the actual ID of the user you want to delete.

## Functionality

### MongoDB Model (User)

The `User` model defines the schema for user data, including `name`, `age`, and `email`.

### GraphQL Schema

The GraphQL schema defines the types and operations supported by the API. It includes types for `User` and operations for querying users, creating users, and deleting users.

### Express Server

The Express server is responsible for handling incoming HTTP requests and forwarding them to the appropriate GraphQL resolver functions.

### Resolvers

Resolvers are functions that resolve GraphQL queries and mutations by fetching data from the database or performing other actions. In this project, resolvers handle CRUD operations for user data.

## Contributing

Contributions are welcome! Please feel free to submit a pull request or open an issue if you encounter any problems.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
