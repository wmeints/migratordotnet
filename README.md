Migrator.NET
==============

This is a clone of the original Migrator.NET code to bring it up to date and to fix a few minor issues.
May be later extended with new features to make it more usable.

## Introduction
Database Migrations implemented in .NET.
Supports rolling up and rolling back of migrations.

A way to integrate database change management into your regular development and automation processes.
The migrations themselves are implemented in code and can be mostly done in a database independent way.

Licensed under MPL 1.1 : http://www.mozilla.org/MPL/

Supported Databases
-------------------
* MySQL (5.0, 5.1)
* PostgreSQL
* SQLite (tested on Mono)
* SQL Server (2000, 2005)
* SQL Server CE (3.5)

Untested Databases but in there
-------------------------------
* Oracle

Supported Modes
---------------
* MSBuild Task
* NAnt Task
* Console Application
* Run from your own application

## Usage

Add bin/Migrator.Framework.dll to you project references
Create a class for your migration like:

    using Migrator.Framework;

    [Migration(1)]
    public class MyMigration : Migration
    {
        public override void Up()
        {
            // Create stuff
        }
        public override void Down()
        {
            // Remove the same stuff
        }
    }


Compile and use your migrations using
- Nant task
- MSBuild task
- Console application
- Run from your own application