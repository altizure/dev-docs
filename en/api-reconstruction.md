# Create Reconstruction Task via API

## Overview
After a project is [created](api-create-project), and images are [uploaded](upload.md), a reconstruction task could be created to start a reconstruction.
This step would cost coin if it is a pro project (without coupon).

### Mutation: startReconstructionWithError()
Send a gql request with the required project id, with an optional coupon id.
The project id is obtained from either the mutation: createProject or query: my.projects.
The coupon id (if any) is obtained from query: my.coupons.
If successful, a new task object would be created and returned.
Otherwise, an error would be returned.
There are 10 types of error.
Details could be found in the GraphiQL docs.

### Example
```js
mutation startReconstructionWithError {
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

### Next
Once a reconstruction task is created. You could get its task state and other info within the Project type via the top level query: project.

---

Last modified at {{ file.mtime }}
