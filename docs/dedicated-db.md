---
layout: default
title: Dedicated database service
parent: Matrix Event Bus (MEB)
grand_parent: SmartClean Matrix
nav_order: 1
---

In cases where it is not possible to host a dedicated HTTPs endpoint or develop the mechanisms to read sensor and event data, write to a database of your choice and query it, Matrix offers a curated solution where we deploy our connector to do this for you.

The advantage of this method is that without any servers to provision or code to manage data flow, you will get access to query your project data using standard SQL.

### What is the dedicated database service
1. A dedicated database instance provisioned for your projects that allows you to query desired data and time series events from sensors.
2. Any standard [PostgreSQL](https://www.postgresql.org) database with the TimeScale extension will work.
3. The database will allow the following kinds of interaction:
   1. You can query data from it.
   2. Our system can write data to it by receiving it from the internal event bus.
   

### Means of data integration
Allow you to query desired data pushed to a database by our platform, such as sensor data and Matrix events. 

1. You may reach out to your account executive to set up the solution for you.
2. You may alternatively, provision your own Timescale DB (PostgreSQL database instance with the TimeScale extension)
 and give us access to write to it.

The diagram below shows how Matrix and subscribers of this service can access this database.

<img alt="Using the dedicated database" src="https://www.smartclean.io/matrix/images/Multi-Tenant-DB.png" title="Using the dedicated database" width="800"/>

Note: The term multi-tenanted data access in the diagram means the database may store data for multiple projects, which
may belong to different tenants (owners).

### Example use case:
Using data queried from the database, you may fulfil or enhance your own use cases.
- Such as, but not limited to:
1. Create or enrich your own digital user interfaces
2. Create or enhance your own data processing and visualisation applications.
3. Design APIs for users of your application to query.

### Use your own SQL database instead
1. You may want to create or use your own SQL database server instead of using the one provided by us.
2. In this case, you control the database server in the environment of your choice.
3. Create a database in the PostgreSQL server for this interaction.
   1. Ensure the database name, username, password you provide us has access to write to it.
   2. Only if the privilege was altered on this database, you need to verify this 
   (default privilege already has this access)
4. When signing up for this service, provide us details for the database connection
  - So that onboarded sensors and events from our Matrix Event Bus can be written to it.
  

### Connecting to the database
1. An authorised connection to this PostgreSQL database is all that is required to start using it.
2. Authorised means that a username and password will be required, since the instance must be secure.
3. For connecting to a PostgreSQL database the following details are required:
   1. **host** - A web URL identifying the database server.
   2. **database** - Name given to the desired database on the server.
   3. **user** - Name of user having access to the database.
   4. **password** - Password for this user.
4. Below are some options for connecting to the database:
   1. Use the PostgreSQL command line interface (psql). 
   2. Use a library available in the programming language of your choice. 
   3. Connect to it from a cloud platform or service of your choice. 
   4. Majority of BI (business intelligence) service providers allow connection to PostgreSQL databases.


### Example of querying the database
Here is an example query that returns the total people count for a time range 
across all the zones (where the people counter is installed) in your building:
 ```
 select insid as Zone, sum(cast(v->>'count' as integer)) TotalPeople from <db.table>
 where pid = '<pid>' and month = '<month>' and dom = '<dom>' and devtype = 'SMARTCLEAN#PPLCTR'
 and time >= <Start Time> and time <= <End Time> group by insid;
 ```
