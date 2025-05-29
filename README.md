1. npm install -g bun   install bun using npm
2. npx create-turbo@latest
3. cd packages
mkdir db
cd db
bun init 
bun install prisma
bunx prisma init


4. 
model User {
  id              String      @id    @default(uuid())
  username        String
  password        String
} 
5. start db using docker locally using this ==> DATABASE_URL="postgresql://postgres:mysecretpassword@localhost:5432/postgres
6. update .env
DATABASE_URL="postgresql://postgres:mysecretpassword@localhost:5432/postgres

7. bunx prisma migrate dev  for the migrate dev  migrate we will not put ci/cd pipeline we will do manually 
8. bunx prisma generate   for the generate   // it can be use in cicd pipeline

9. import { PrismaClient } from "@prisma/client";

export const prismaClient; put in index.ts

10. update in package.json  inside of  the packages/db "exports": {
	"./client": "./index.ts"
}


<=====================================Now  we will create backend where we will use the db things===============>
1. cd apps
mkdir backend
cd backend
bun init

2. bun install express @types/express
3. update in the package.json "dependencies": {
	"db": "*"
} inside in the backend  package.json

4. bun install     do this globally in root folder which is turbo folder

5. inside of the backend index.tx you can db import like this 
import { prismaClient } from "db/client";   ==>client this already told in the package.json in the export in the packages/db then package.json   whatever you give the name that name should be like that   and db is the package name so that is why


<==========================================================end of the initialized===========================>
Now we will do the Docker things
