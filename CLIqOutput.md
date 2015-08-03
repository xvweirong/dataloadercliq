# Introduction #
Every CLIq project will have a process name which is used to create the directory structure.  In this document _process_ indicates the process name you select.

# Files and Directories #

## Directories ##
  * _process_ : The base directory for all CLIq files related to this process.
  * _process_/config : Configuration files such as process-conf.xml, sdl, and config.properties
  * _process_/log : success/error logs, run files
  * _process_/read : source files for CSV read operations (DML)
  * _process_/write : destination for CSV write operations (Exports from Salesforce)

## Files ##
  * _process_.bat : Windows Batch file to run your process.  You can schedule this file to run automatically using Windows Scheduler.
  * _process_.sh : UNIX shell script to run your process.  You can schedule this file to run automatically using cron.
  * _process_/config/process-conf.xml: Main configuration file.  See the Data Loader documentation for details on each parameter.

# Notes #