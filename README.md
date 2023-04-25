# Introduction

bzAuditLog is an audit logging module for Claris FileMaker 2023+.

## Quickstart

- Requires Claris FileMaker 2023 or higher.

1. Copy or Import the `AuditLog` and `SchemaLog` tables into your solution
1. Copy the `OnWindowTransaction` field into every table you want to audit. Tip: To avoid the field being commented out, ensure that you change the recordPrimaryKey property to match the primary key field of the target table. If the table doesn't have a primary key, set the `recordPrimaryKey` property to a blank string
1. Copy or import the `Audit` script into the script workspace
1. In `File > File Options > Script Triggers` set the OnWindowTransaction script trigger to run the `Audit` script

That's it. Changes will now be logged for all tables. Record data will be logged for all tables with the `OnWindowTransaction` field.

## Fine tuning

- To entirely exclude tables from being logged, add them to the list in the `If` step on line 38
- To change the fields that get logged for a table, edit the `ExecuteSQL` query in the `OnWindowTransaction` field definition for that table