# Prisma Starter Project
This repo is targeting for Prisma usage with existing Database.
For new project, it may need to take a different approach, for example building model from Prisma schema. For 
details go [here](https://www.prisma.io/docs/getting-started/setup-prisma/start-from-scratch).

## How to start
- Copy `.env.template` in the root folder and name it `.env`. Adjust the value as needed.
- Generating model `npx prisma db pull`. The model will be added into `./prisma/schema.prisma`. If there is any 
  change in the DB schema, execute the command to have the generated model synced.
- Generating code `npx prisma generate`. This command will generate a folder `./node_modules/.prisma`

### Example usage of the generated client in the code
```javascript
const { PrismaClient } = require('@prisma/client');
const prisma = new PrismaClient();
const merchant = await prisma.merchant.findFirst(
    {where: {'field': 'value'}}
);
```

Available default functions for each model
```
findUnique: [Function (anonymous)]
findFirst: [Function (anonymous)]
findMany: [Function (anonymous)]
create: [Function (anonymous)]
createMany: [Function (anonymous)]
delete: [Function (anonymous)]
update: [Function (anonymous)]
deleteMany: [Function (anonymous)]
updateMany: [Function (anonymous)]
upsert: [Function (anonymous)]
count: [Function (anonymous)]
aggregate: [Function (anonymous)]
groupBy: [Function (anonymous)]
```
---
#### Note 
For code completion, make sure that folder `node_modules/.prisma` is included as source folder.
You can include or exclude the folder from `.gitignore` based on your project setup. 
