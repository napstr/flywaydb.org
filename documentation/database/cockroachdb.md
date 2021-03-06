---
layout: documentation
menu: cockroachdb
subtitle: CockroachDB
---
# CockroachDB

## Supported Versions

- `2.0`
- `1.1`

## Driver

<table class="table">
<thead>
<tr>
<th></th>
<th>PostgreSQL</th>
</tr>
</thead>
<tr>
<th>Supported versions</th>
<td><code>9.3-1104-jdbc4</code> and later</td>
</tr>
<tr>
<th>URL format</th>
<td><code>jdbc:postgresql://<i>host</i>:<i>port</i>/<i>database</i></code></td>
</tr>
<tr>
<th>Ships with Flyway Command-line</th>
<td>Yes</td>
</tr>
<tr>
<th>Maven Central coordinates</th>
<td><code>org.postgresql:postgresql:42.1.4</code></td>
</tr>
<tr>
<th>Default Java class</th>
<td><code>org.postgresql.Driver</code></td>
</tr>
</table>

## SQL Script Syntax

- [Standard SQL syntax](/documentation/migrations#sql-based-migrations#syntax) with statement delimiter **;**

### Compatibility

- DDL exported by pg_dump can be used unchanged in a Flyway migration.
- Any CockroachDB sql script executed by Flyway, can be executed by the CockroachDB command-line tool and other
        PostgreSQL-compatible tools (after the placeholders have been replaced).

### Example

<pre class="prettyprint">/* Single line comment */
CREATE TABLE test_data (
 value VARCHAR(25) NOT NULL PRIMARY KEY
);


/*
Multi-line
comment
*/

-- Placeholder
INSERT INTO ${tableName} (name) VALUES (&#x27;Mr. T&#x27;);</pre>

## Limitations

- No support for psql meta-commands with no JDBC equivalent like `\set`

<p class="next-steps">
    <a class="btn btn-primary" href="/documentation/database/saphana">SAP HANA <i class="fa fa-arrow-right"></i></a>
</p>