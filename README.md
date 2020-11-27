# MvcMovie
Demo asp.net website based on MVC with MySQL db


# Requirements for running MvcMovie locally
This application is built on .NET 5 and connects to a MySQL db. 

## Install .NET 5
Head over to https://dotnet.microsoft.com/download/dotnet/5.0 and download the SDK 5.0.100. Install it.

## Install MySQL Server
Grab the MySQL installer from https://dev.mysql.com/downloads/installer/. You need at least the MySQL Server, but you can choose additional components if you like. 

When you get to the point of choosing the root password, pick 'root'. MvcMovie is expecting to log in with user 'root' and password 'root'. If you have configured another
root password or user account, you can always edit the connection string inside MvcMovie located inside the **appsettings.json** file.

## Setup MySQL database
!!If you cannot access mysql from the command prompt, add the bin folder of your MySQL Server
installation to your PATH environment variable. The path to the bin folder should look like this "C:\Program Files\MySQL\MySQL Server 8.0\bin".


Open a command prompt and execute 

`mysql -u root -p`. 

Enter the root password. Then create a database called "movies" and create a table "movie" with some columns like this:

    CREATE DATABASE movies;
    USE movies;
    CREATE TABLE `movie` (
      `Id` bigint(20) NOT NULL AUTO_INCREMENT,
      `Title` varchar(20) NOT NULL,
      `ReleaseDate` date NOT NULL,
      `Genre` varchar(20) NOT NULL,
      `Price` decimal(18,2) NOT NULL,
      `Rating` varchar(20) NOT NULL,
      PRIMARY KEY (`Id`)
    ) ENGINE=InnoDB AUTO_INCREMENT=10 DEFAULT CHARSET=latin1;
    
Execute the mysql interface by typing `exit`.

## Running MvcMovie
Open a command prompt and `cd` into the MvcMovie folder, heading all the way to the project level (where the .csproj is located).
Now all you need to do is execute dotnet run:

    dotnet run

Exit the application with a Ctrl+c combination inside the command prompt.


Enjoy!
