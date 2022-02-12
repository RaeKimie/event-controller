## access database through amplify
amplify add api
- can select rest api / graphQL (going to select graphQL)
- give a name
- choose authentication method - go for cognito user pool
- Done
- no schema, generate one (single object / one to many relationship/ objects with fine-grained access control ex project management app with owner-based authorization)
- y to add schema -> amplify backend folder changed

> note: nice to search about graphQL, app with more complicated backend etc

- go to schema and change the schema name
    {id, title, description, filePath, like, owner}

- amplify push
6:11

https://youtu.be/kqi4gPfdVHY