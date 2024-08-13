# RAG Resume

## Prequisites
### Create Cluster 
- Create a MongoDB Atlas account at https://cloud.mongodb.com
- Create an Atlas Cluster
  - Select "Shared"
  - Cloud Provider: AWS
  - Region: us-east-1
  - Cluster Tier: M2
  - Cluster Name: search-demo
 
### Create Database User
- Navigate to Database Access
- Create a database user
  - username: demo
  - password: demo

### Configure Network Access
- Navigate to Network Access
- Select Add IP Address
- Select "Allow Access from Anywhere"

- ### Get Atlas Connection String
- Select "Connect"
- Select "Drivers"
- Select "Python" and Select Python driver version from drop down
- Copy the Connection String
This will be the MongoDB Atlas Connection String. Replace username / password with demo / demo.

### Create database and collection
- Database: resume
- Collection: coll

### Search Index
- Navigate to Atlas Search and select "Create Search Index"
- Create Vector Search index using json editor
- Database and Collection: resume.col
- Index Name: default
- Index definition, refer to ```vector-index.json```
```
{
    "fields": [
      {
        "numDimensions": 1536,
        "path": "embedding",
        "similarity": "cosine",
        "type": "vector"
      }
    ]
  }

