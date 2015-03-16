# Changelog

## 0.7.0    2015-03-16

* Reset-less collector
  * Calculate the diff on the receiver end for simplicity's sake
  * Don't run pg_stat_statements_reset() anymore
  * Make --no-reset option a no-op (will be removed soon)
* Restricted privileges
  * Added support for using a monitoring user (see README)
  * Removed hard superuser requirement
* Don't collect query information from pg_stat_activity (it might be sensitive)
  * Remove --no-query-parameters option, its a no-op now
* Collect replication statistics
* Add option for disabling collection of postgres locks & config settings
* Remove support for pg_stat_plans, its not supported anymore
* Update vendored pg8000 to latest version (1.10.1)


## 0.6.4    2014-11-17

Fixes:

* Do not require dbhost to be set


## 0.6.3    2014-11-16

Re-release to fix build issues


## 0.6.2    2014-11-13

Fixes:

* CREATE EXTENSION IF NOT EXISTS pg_stat_statements
* Auto-detect Amazon Web Service DB hosts as remote


## 0.6.1    2014-07-26

Fixes:

* Drop dmidecode dependency to gather server vendor/model on Linux
* Fix whitespace in generated configuration file


## 0.6.0    2014-07-18

Features & improvements:

* support for pg8000 as psycopg2 replacement
* collector can now be run from a zip file
* Split collector into separate modules
* import pg8000 & colorama
* Add conversation module for setup wizard
* Support for packaging to deb & rpm using fpm
* Move zip building to Makefile

Fixes:

* Don't replace newlines in collected queries with whitespace
* Ignore queries belonging to other databases


## 0.5.0	2014-01-24

* pg_stat_statements support


## 0.4.0	2013-12-04

* Switch from psql wrapper to psycopg2


## 0.3.2	2013-08-13

* Collect CPU information from OS
* Ignore queries created by the collector


## 0.3.1	2013-07-23

* Collecting more Postgres Information
  * GUCs (configuration settings)
  * BGWriter
  * backends
  * locks


## 0.3.0	2013-04-03

* Collect information about Postgres schema
  * Tables
  * Indexes
  * Bloat


## 0.2.0	2013-02-22

* Switch to Python
* dry-run mode - see data before it's posted
* privacy mode - don't send query examples to API
* Collect OS (CPU, memory, storage) information


## 0.1.4	2013-02-06

* Small fixes to config parsers and plan fetching


## 0.1.2	2013-01-29

* dry-run mode


## 0.0.1	2012-12-22

* Initial release of the Ruby Collector
* Support for fetching information from pg_stat_plans
