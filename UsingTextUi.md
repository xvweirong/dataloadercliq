# Using CLIq Text UI #
You can use either the graphical or text user interface.  If you ran the GUI, you can skip to "Using the Files" below.
![http://lh4.ggpht.com/_alGXTM7ympw/SyabvfVQEQI/AAAAAAAAA-c/FSgxWiYqFnc/s400/cmdline.jpg](http://lh4.ggpht.com/_alGXTM7ympw/SyabvfVQEQI/AAAAAAAAA-c/FSgxWiYqFnc/s400/cmdline.jpg)
  1. In the cliq directory, run:
```
cliq.bat -t
```
  1. Choose an operation:
```
1. Export
2. Insert
3. Update
4. Upsert
5. Delete
Enter a menu option:
```
  1. Enter a process name:
```
Each process needs a unique indentifier.  Use word characters only.
Enter the name of your process: export accounts
```
    * This string will be used to create the directories and files
    * The process name will identify the process in the process-conf.xml.
  1. Enter your Salesforce username/password:
```
Enter your username: vswamidass@dev.salesforce.com
Enter your password: 
```
    * The username/password combination will be verified with Salesforce
    * Password will be encrypted in process-conf.xml.
  1. If you selected _Export_, enter the SOQL query to export:
```
Enter your query: select id,name,ownerid from account
```
    * If your query has errors, you will receive an error message
    * CLIq will extract the object name from your query
  1. After CLIq runs successfully, the CLI files will be located in the _processname_ directory under the cliq directory.

See [UsingCLIqFiles](UsingCLIqFiles.md) for steps on using the output files from CLIq.