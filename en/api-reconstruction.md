# How to do 3D reconstruction via API

### Overview

3D reconstruction service is provided as a project on Altizure. You need to create a project in order to trigger a 3D reconstruction task.
Each user could create multiple projects. But one project could only be owned by one user.
The project created via API is owned by the user whose user token is passed along the request.

### 1. Create a project
Send a GraphQL request with your application key and user token (not necessarily your own).
Call with the required project name (not necessarily unique), and optional project type (free or pro).
This step would not cost any coin to run.
But if the coin balance is not enough for the pro project, it is not allowed to start a reconstruction task.
If successful, the Project type will be returned, otherwise it would be null.
From this type, you could get the id field.
This project id is used as an argument in all of the project related queries and mutations.

__Sample GraphQL request__
```js
mutation {
  createProject(name: "sample project", type: free) {
    id
  }
}
```

### 2. Upload images
After a project is created, you can start to let users upload images as [upload image tutorial](upload.md).
When the upload finishes, a reconstruction task could be created to start a reconstruction.

### 3. Start the reconstruction
Send a GraphQL request with the required project id, with an optional coupon id.
The project id is obtained from either the mutation: createProject or query: my.projects.
The coupon id (if any) is obtained from query: my.coupons.
This step would cost coin if it is a pro project (without coupon).


If successful, a new task object would be created and returned.
Otherwise, an error would be returned.
There are 10 types of error.
Details could be found in the GraphQL docs.

__Sample GraphQL request__
```js
mutation {
  startReconstructionWithError(id: "54ed8e5741fbfa3e1967fe9b") {
    error {
      code
    }
    task {
      id
      state
    }
  }
}
```

### 4. Check project status
Once a reconstruction task is created. You could get its task state and other info within the Project type via the top level query: project.


---

Last modified at {{ file.mtime }}
