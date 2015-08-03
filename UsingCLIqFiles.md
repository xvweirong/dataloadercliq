  * A directory name will be created using the process name you entered.  For example, if your process name is `import accounts`, CLIq will create a directory called `import_accounts`.
    * Cliq 1.2: The process directory will be under _dataloaderhome_/cliq
    * Cliq > 1.2: The process directory will be under _dataloaderhome_/cliq\_process
  * **For DML Opertations (Insert, Update, Upsert, Delete), you will need to complete the configuration manually.  See [ConfiguringDml](ConfiguringDml.md) for instructions.**
  * To run the script
    * On Windows, open the _processname_ directory and run _processname_.bat.
    * On UNIX
      1. cd _processname_
      1. chmod 700 _processname_.sh
      1. ./_processname_.sh
  * To automate
    * On Windows, use Windows Scheduler to run _processname_.bat.
    * On UNIX, use cron to run _processname_.sh.
  * For a complete reference to all the CLI options and parameters, see the Salesforce CLI documentation http://wiki.developerforce.com/index.php/Using_Data_Loader_from_the_command_line