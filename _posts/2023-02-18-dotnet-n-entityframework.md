---
title: dotnet and . NET Entity Framework
date: 2023-02-18 16:30
---
<!-- markdownlint-disable -->
<p>The Intro to Programming @ Progressive has come to an end. I loved every second of it; loved hearing a pro speak of what to expect as very reassuring.
The instructor explained everything clearly and gave us all a lot of tips and advice to succeed in our career as Apps Programmers. The emphasis of loose coupling was made clearer.
Learned neat tricks to use Visual Studio and Visual Studio Code. We were able to create a frontend application and the backend where it connects to a database (SQL Server).
I took it upon myself to recreate (run) the application using the CLI.... I left my notes at the office (my parents' house) to create a proper write-up lest I forget the commands.
</p>

<p>The following list of commands is to install dotnet Entity Framework, add a new migration and update the database (creating the table). This example assumes the code is ready to go and the database is listening to connections; this was done using Docker.</p>

    

```BASH
    # get the package
    dotnet tool install --global dotnet-ef

    # add the Entity Framework to the project
    dotnet add package Microsoft.EntityFrameworkCore.Design

    # add a new migration
    dotnet ef migrations add

    # update the database to a specified migration
    dotnet ef database update <migration ID>   
```

<p>note: the connection string can be added to the appSettings.json file.</p>

<p>'till next time</p>
Jose
