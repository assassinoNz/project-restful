# Type-Safe, Fast and Collaborative Development Workflow with Node.js + Express.js

## Prerequisites
- MySQL (Tested on 8.0.35)
- node.js (Tested on 20.10.0)
- npm (Tested on 10.2.3)

## Deployment Setup
### 1. Install dependencies

- Run `$ npm install --omit=dev`.

### 2. Create and update configuration variables

- Run `$ touch .env`.

- Copy the following content.

<pre>
;Set this to 'development' if console logs are needed.
;Set this to 'production' to mute console logs
;File-based logs are enabled regardless of the setting
NODE_ENV = "development"

;MySQL databse location
MYSQL_URL = "mysql://{username}:{password}@localhost:3306/{db_name}"

;Port used for Express server
EXPRESS_PORT = 8080

;Default number of items to include in a response list
PAGE_SIZE = 10
</pre>

- Modify the values in `.env` accordingly.

- Make sure `NODE_ENV = "production"`.

### 3. Create the database

- `$ npm run prisma:push`.

## Development Setup
### 1. Perform the "Deployment Setup" above

- Make sure `NODE_ENV = "development"`.

### 2. Install development dependencies

- Make sure `npm install`.

### 3. Design the database schema

- Do the necessary changes in the `prisma/schema.prisma"` file.
- Sync the changes to the database using `$ npm run prisma:push`.
- The changes will be propagated across the project as error by Typescript.

### 4. Design the API schema

- Do the necessary changes in the `zodios/api.ts` file.
- The changes will be propagated across the project as error by Typescript.

### 5. Do the development

- Use `src` directory.
- As a best practice, look for any typescript errors and fix them first.

### 6. Develop test cases

- Use `test` directory.

## Start server

- `$ npm run start`
- Visit `http://localhost:<EXPRESS_PORT>/docs/v1` to view the API docs.

## Resources
### 1. ERD
![Autogenerated ERD of the system](./prisma/ERD.svg)