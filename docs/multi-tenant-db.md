---
layout: default
title: Multi-tenant database service
parent: Matrix Event Bus (MEB)
grand_parent: SmartClean Matrix
nav_order: 1
---

### What is a multi-tenant database
Multi-tenant means shared, referring to the same database instance which can be queried by authorized clients.

Any standard [PostgreSQL](https://www.postgresql.org) database will work.

The database we use for this is called [TimeScale DB](https://docs.timescale.com) which is provided as an
 extension to PostgreSQL.


### Means of data integration
Clients who subscribe for this service can connect to this database and query it for desired data.

Below diagram shows how SmartClean Matrix and subscribers of this service can access this database.

<img alt="Using the multi-tenant database" src="https://www.smartclean.io/matrix/images/Multi-Tenant-DB.png" title="Using the multi-tenant database" width="800"/>


### Example use case:
Using various data and events from our platform, you can fulfil or enhance your own use cases:
- Make or enrich your own digital user interface, or
- Make or enrich your own data processing and visualisation application. 

- Subscribe for this service
  - To be able to create a dedicated connection to the database instance
- Run your queries on the database using this connection
  - To get desired data and use it accordingly.


### Use your own SQL database instead
You may want to create or use your own SQL database instead of using the one provisioned by us.

- In this case, you take care of creating the SQL database in the environment of your choice.

- When signing up for this service, provide us details of a database connection
  - So that onboarded sensors and events from our Matrix Event Bus can be written to it.
  

### Connecting to the database
An authorised connection to this PostgreSQL database is all that is required to start using it.

Authorised means that a username and password will be required, since the instance must be secure.

For connecting to a PostgreSQL database the following details are required:
1. **host** - A web URL identifying the database server.
2. **database** - Name given to the desired database on the server.
3. **user** - Name of user having access to the database.
4. **password** - Password for this user.

Note: These details are required whether the database is provided by us or provided by you. 

Below are some options for connecting to the database:
- Use the PostgreSQL command line interface.
- Use a library available in the programming language of your choice.
- Connect to it from a cloud platform or service of your choice. 
- Majority of BI (business intelligence) service providers also allow you to connect to any PostgreSQL databases.

### Example of querying the database
Here is an example query that returns the total people count for a time range 
across all the zones (where the people counter is installed) in your building:
 ```
 select insid as Zone, sum(cast(v->>'count' as integer)) TotalPeople from <db.table>
 where pid = '<pid>' and month = '<month>' and dom = '<dom>' and devtype = 'SMARTCLEAN#PPLCTR'
 and time >= <Start Time> and time <= <End Time> group by insid;
 ```
