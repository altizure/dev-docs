# Create Project via API

## Overview
Each user could create multiple projects. But one project could only be owned by one user.
The project created via API is owned by the user whose user token is passed along the request.

### Mutation: createProject()
Send a gql request with your application key and user token (not necessarily your own).
Call with the required project name (not necessarily unique), and optional project type (free or pro).
This step would not cost any coin to run.
But if the coin balance is not enough for the pro project, it is not allowed to start a reconstruction task.
If successful, the Project type will be returned, otherwise it would be null.
From this type, you could get the id field.
This project id is used as an argument in all of the project related queries and mutations.

### Example
```js
mutation {
  createProject(name: "Archaeology", type: free) {
    id
  }
}
```

### Next
Once a project is created and its project id is obtained. You could upload images into it via the [upload API](upload.md).

---

Last modified at {{ file.mtime }}
