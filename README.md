# Introduction

The repository is about to compare the method `IMapper.Map` and the extension `ProjectTo`.

Given a context below:
- A database having a table named `Student` with columns `ID`, `Name`, `Grade`. A sample data of 6 records are inserted.
- In source code, we have 
  - an entity `Student` with properties `ID`, `Name`, and `Grade`
  - a DTO `StudentDto` with properties `Name`, `Grade`.

Execute a simple `SELECT` query with two different mapping methods, then observe the output.

**A. EF Core version `6`, AutoMapper verion `7.0.1`**
- Using `IMapper.Map`
  - The number of records returned: 6
  - The number of query execution: 1
  - The actual query: `SELECT ID, Name, Grade FROM Student`

- Using `ProjectTo`
  - The number of records returned: 6
  - The number of query execution: 1
  - The actual query: `SELECT Name, Grade FROM Student` (`ID` is not included)

**B. EF Core verion `3.1.22`**

**TBC**

# Setup

- Create a database named `Student` on a SQL Server instance.
- Prepare a text file `connectionstring.txt` containing the database above, then put it in folder `EFCoreAndAutoMapper`
- On folder `EFCoreAndAutoMapper`, open a terminal and execute command `dotnet ef database update`.
- Launch project `EFCoreAndAutoMapper` and check out on the console screen.
