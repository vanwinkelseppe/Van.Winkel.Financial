# Van.Winkel.Financial

## Important

In the following files: `./scripts/sql-scripts/create-user.sql` & `.scripts/01-migrate-db.sh` we use placeholder values for a user and a database. Do not use this in an actual production environment.

## How to run

### Remarks

Option for in memory database is also a possibility just comment the line in Startup.cs that says 'UseSqlServer' and uncomment 'UseInMemory'


### 0. Build solution

Navigate to `.src` and run `dotnet build`

### 1. Create database & user 

Go to `.scripts/` and execute the script using cmd `sh 00-create-db.sh` you can also create a user and database manualy for example on azure and provide the connectionstring in the next steps.

### 2. Migrate database

Go to `.scripts/` and execute the script using cmd `sh 01-migrate-db.sh` edit the file if you didn't follow step 1 and created a database manually. 
Alternatively you can navigate to `.\src\Van.Winkel.Financial.Database\bin\Debug\netcoreapp3.1` and execute `dotnet Van.Winkel.Financial.Database.dll -c "$(ConnectionString)"`


### 3. Run project 

#### 3.1 Frontend

Go to `.\src\Van.Winkel.Financial.Frontend` and execute `npm run build`. This will build the frontend and place it in the wwwroot of the application.

#### 3.2 Backend


Open project `.\src\Van.Winkel.Financial.sln` in visual studio and press run with `Van.Winkel.Financial.Host` as startup project.


### 4. Run tests

Go to `.\src\` and execute `dotnet test`

