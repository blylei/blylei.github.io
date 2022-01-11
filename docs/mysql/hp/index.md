# MySQL-高性能篇

| Language  | ORM | YSQL Drivers | YCQL Drivers |
| --------- | --- | ------------ | ------------ |
| Java  | [Spring/Hibernate](https://docs.yugabyte.com/latest/quick-start/build-apps/java/ysql-spring-data/) | [PostgreSQL JDBC](https://docs.yugabyte.com/latest/quick-start/build-apps/java/ysql-jdbc/) | [cassandra-driver-core-yb](https://docs.yugabyte.com/latest/quick-start/build-apps/java/ycql/)
| Go  | [Gorm](https://github.com/yugabyte/orm-examples) | [pq](https://docs.yugabyte.com/latest/quick-start/build-apps/go/#ysql) | [gocql](https://docs.yugabyte.com/latest/quick-start/build-apps/go/#ycql)
| NodeJS  | [Sequelize](https://github.com/yugabyte/orm-examples) | [pg](https://docs.yugabyte.com/latest/quick-start/build-apps/nodejs/#ysql) | [cassandra-driver](https://docs.yugabyte.com/latest/quick-start/build-apps/nodejs/#ycql)
| Python  | [SQLAlchemy](https://github.com/yugabyte/orm-examples) | [psycopg2](https://docs.yugabyte.com/latest/quick-start/build-apps/python/#ysql) | [yb-cassandra-driver](https://docs.yugabyte.com/latest/quick-start/build-apps/python/#ycql)
| Ruby  | [ActiveRecord](https://github.com/yugabyte/orm-examples) | [pg](https://docs.yugabyte.com/latest/quick-start/build-apps/ruby/#ysql) | [yugabyte-ycql-driver](https://docs.yugabyte.com/latest/quick-start/build-apps/ruby/#ycql)
| C#  | [EntityFramework](https://github.com/yugabyte/orm-examples) | [npgsql](http://www.npgsql.org/) | [CassandraCSharpDriver](https://docs.yugabyte.com/latest/quick-start/build-apps/csharp/#ycql)
| C++ | Not tested | [libpqxx](https://docs.yugabyte.com/latest/quick-start/build-apps/cpp/#ysql) | [cassandra-cpp-driver](https://docs.yugabyte.com/latest/quick-start/build-apps/cpp/#ycql)
| C   | Not tested | [libpq](https://docs.yugabyte.com/latest/quick-start/build-apps/c/#ysql) | Not tested


## Current roadmap

Here is a list of some of the key features being worked on for the upcoming releases (the YugabyteDB [**v2.11 latest release**](https://blog.yugabyte.com/announcing-yugabytedb-2-11/) has been released in **November, 2021**, and the [**v2.8 stable release**](https://blog.yugabyte.com/announcing-yugabytedb-2-8/) was released in **October 2021**).

| Feature                                         | Status    | Release Target | Progress        |  Comments     |
| ----------------------------------------------- | --------- | -------------- | --------------- | ------------- |
|[Upgrade to PostgreSQL v13](https://github.com/yugabyte/yugabyte-db/issues/9797)| PROGRESS| v2.13 |[Track](https://github.com/yugabyte/yugabyte-db/issues/9797)| For latest features, new PostgreSQL extensions, performance, and community fixes
|[Change Data Capture](https://github.com/yugabyte/yugabyte-db/issues/9019)| PROGRESS| v2.13 |[Track](https://github.com/yugabyte/yugabyte-db/issues/9019)|Allows multiple downstream apps and services to consume changes from YugabyteDB|
|Support for  [in-cluster PITR](https://github.com/yugabyte/yugabyte-db/issues/7120)  | PROGRESS| v2.13 |[Track](https://github.com/yugabyte/yugabyte-db/issues/7120)|Point in time recovery of YSQL databases, to a fixed point in time, across DDL and DML changes|
|[Support for materalized views](https://github.com/yugabyte/yugabyte-db/issues/10102) | PROGRESS| v2.13 |[Track](https://github.com/yugabyte/yugabyte-db/issues/10102)|Support create, drop, refresh materialized view|
|[Geo-partitioning support](https://github.com/yugabyte/yugabyte-db/issues/9980) for the transaction status table |PROGRESS| v2.13 |[Track]()|Allows creating multiple transaction status tables|
| [Automatic tablet splitting enabled by default](https://github.com/yugabyte/yugabyte-db/blob/master/architecture/design/docdb-automatic-tablet-splitting.md) | PROGRESS  | v2.13 | [Track](https://github.com/yugabyte/yugabyte-db/issues/1004) |Enables changing the number of tablets (which are splits of data) at runtime.|
| YSQL-table statistics and cost based optimizer(CBO) | PROGRESS  |  v2.13 | [Track](https://github.com/yugabyte/yugabyte-db/issues/5242) | Improve YSQL query performance |
| [YSQL-Feature support - ALTER TABLE](https://github.com/yugabyte/yugabyte-db/issues/1124) | PROGRESS | v2.13 | [Track](https://github.com/yugabyte/yugabyte-db/issues/1124) | Support for various `ALTER TABLE` variants |
| [YSQL-Online schema migration](https://github.com/yugabyte/yugabyte-db/blob/master/architecture/design/online-schema-migrations.md)  | PROGRESS  | v2.13 | [Track](https://github.com/yugabyte/yugabyte-db/issues/4192) | Schema migrations(includes DDL operations) to be safely run concurrently with foreground operations |
| [Row-level geo-partitioning](https://github.com/yugabyte/yugabyte-db/blob/master/architecture/design/ysql-row-level-partitioning.md) | PROGRESS  |  v2.13 | [Track](https://github.com/yugabyte/yugabyte-db/issues/1958) | Enhance YSQL language support |
| Transparently restart transactions | PROGRESS  | v2.13 | [Track](https://github.com/yugabyte/yugabyte-db/issues/5683) | Decrease the incidence of transaction restart errors seen in various scenarios |
| Pessimistic locking Design | PROGRESS  | v2.13  | [Track](https://github.com/yugabyte/yugabyte-db/issues/5680) |  |
| Make [`COLOCATED` tables](https://github.com/yugabyte/yugabyte-db/blob/master/architecture/design/ysql-colocated-tables.md) default for YSQL | PLANNING  |  | [Track](https://github.com/yugabyte/yugabyte-db/issues/5239)  |  |
| Support for transactions in async [xCluster replication](https://github.com/yugabyte/yugabyte-db/blob/master/architecture/design/multi-region-2DC-deployment.md) | PLANNING  |    | [Track](https://github.com/yugabyte/yugabyte-db/issues/1808) | Apply transactions atomically on consumer cluster. |
| Support for GiST indexes | PLANNING  |    | [Track](https://github.com/yugabyte/yugabyte-db/issues/1337) |Suppor for GiST (Generalized Search Tree) based index|

## Recently released features

| Feature                                         | Status    | Release Target | Docs / Enhancements |  Comments     |
| ----------------------------------------------- | --------- | -------------- | ------------------- | ------------- |
| [YSQL-Support `GIN` indexes](https://github.com/yugabyte/yugabyte-db/blob/master/architecture/design/ysql-gin-indexes.md) |  ✅ *DONE*  | v2.11 | [Docs](https://docs.yugabyte.com/latest/explore/ysql-language-features/gin/) | Support for generalized inverted indexes for container data types like jsonb, tsvector, and array |
| [YSQL-Collation Support](https://github.com/yugabyte/yugabyte-db/blob/master/architecture/design/ysql-collation-support.md)  | ✅ *DONE*  | v2.11           |[Docs](https://docs.yugabyte.com/latest/explore/ysql-language-features/collations/) |Allows specifying the sort order and character classification behavior of data per-column, or even per-operation according to language and country-specific rules           |
[YSQL-Savepoint Support](https://github.com/yugabyte/yugabyte-db/blob/master/architecture/design/savepoints.md)  |  ✅ *DONE*  | v2.11     |[Docs](https://docs.yugabyte.com/latest/explore/ysql-language-features/savepoints/) | Useful for implementing complex error recovery in multi-statement transaction|
| [xCluster replication management through Platform](https://github.com/yugabyte/yugabyte-db/blob/master/architecture/design/platform-xcluster-replication-management.md) | ✅ *DONE* | v2.11           |   [Docs](https://docs.yugabyte.com/latest/yugabyte-platform/create-deployments/async-replication-platform/)     |   
| [Spring Data YugabyteDB module](https://github.com/yugabyte/yugabyte-db/blob/master/architecture/design/spring-data-yugabytedb.md) | ✅ *DONE*  | v2.9 | [Track](https://github.com/yugabyte/yugabyte-db/issues/7956) | Bridges the gap for learning the distributed SQL concepts with familiarity and ease of Spring Data APIs |
| Support Liquibase, Flyway, ORM schema migrations | ✅ *DONE* | v2.9           |           [Docs](https://blog.yugabyte.com/schema-versioning-in-yugabytedb-using-flyway/)      | 
| [Support `ALTER TABLE` add primary key](https://github.com/yugabyte/yugabyte-db/issues/1124) | ✅ *DONE* | v2.9 | [Track](https://github.com/yugabyte/yugabyte-db/issues/1124) |  |
| [YCQL-LDAP Support](https://github.com/yugabyte/yugabyte-db/issues/4421) |  ✅ *DONE*  | v2.8           |[Docs](https://docs.yugabyte.com/latest/secure/authentication/ldap-authentication-ycql/#root)  | support LDAP authentication in YCQL API |             
| [Platform Alerting and Notification](https://blog.yugabyte.com/yugabytedb-2-8-alerts-and-notifications/) | ✅ *DONE* | v2.8  |  [Docs](https://docs.yugabyte.com/latest/yugabyte-platform/alerts-monitoring/alert/) |  To get notified in real time about database alerts, user defined alert policies notify you when a performance metric rises above or falls below a threshold you set.|      
| [Platform API](https://blog.yugabyte.com/yugabytedb-2-8-api-automated-operations/) | ✅ *DONE* | v2.8           |   [Docs](https://api-docs.yugabyte.com/docs/yugabyte-platform/ZG9jOjIwMDY0MTA4-platform-api-overview)              |   Securely Deploy YugabyteDB Clusters Using Infrastructure-as-Code|            
