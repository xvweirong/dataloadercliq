# Introduction #
If you have not installed CLIq, please follow the [Installation](Installation.md) instructions.

# Configuration #
To configure proxy support, enter your proxy settings in `cliq.properties`:
```
# 
# CLIq.properties
#

### All of these properties are Optional ###

#Set your Salesforce username and password 
sfdc.username=
sfdc.password=

# i.e. proxy.company.com
sfdc.proxyHost=
# i.e. 8080
sfdc.proxyPort=
sfdc.proxyNtlmDomain=
sfdc.proxyUsername=
sfdc.proxyPassword=

# Use https://test.salesforce.com/services/Soap/u/<YOUR DATA LOADER VERSION> for Sandbox instances
# NOTE: Make sure the version is equal or lower than your version of Data Loader.
#
# For example:
# sfdc.endpoint=https://test.salesforce.com/services/Soap/u/21.0
```

To use CLIq with Sandbox, uncomment the sfdc.endpoint line.

# Starting CLIq #
To run CLIq, run cliq.bat on Windows or cliq.sh on UNIX.

# Using Graphical UI #
Using the GUI is the default mode.  If you prefer a text based interface, please go to [UsingTextUi](UsingTextUi.md).
### 1. Choose an Operation ###
> ![http://lh4.ggpht.com/_alGXTM7ympw/SyKSa5vOA5I/AAAAAAAAA9c/wVQNEE6RedQ/s400/operation.png](http://lh4.ggpht.com/_alGXTM7ympw/SyKSa5vOA5I/AAAAAAAAA9c/wVQNEE6RedQ/s400/operation.png)
The process name is a string which is used to identify your process.  Example: `Export_Accounts`
### 2. Login ###
> ![http://lh5.ggpht.com/_alGXTM7ympw/SyKPZjxA0XI/AAAAAAAAA9I/ySzXHYb5p34/s400/login.png](http://lh5.ggpht.com/_alGXTM7ympw/SyKPZjxA0XI/AAAAAAAAA9I/ySzXHYb5p34/s400/login.png)

### 3. Enter Query or Entity ###
  * SOQL Query for Export (See [SOQL Documentation](http://www.salesforce.com/us/developer/docs/api/index_Left.htm#StartTopic=Content/sforce_api_calls_soql.htm) for more information.)
> ![http://lh6.ggpht.com/_alGXTM7ympw/SyKPZzjczkI/AAAAAAAAA9Q/M2CI4MucEyA/s400/query.png](http://lh6.ggpht.com/_alGXTM7ympw/SyKPZzjczkI/AAAAAAAAA9Q/M2CI4MucEyA/s400/query.png)
  * Entity for  Insert, Update, Upsert, or Delete
> ![http://lh5.ggpht.com/_alGXTM7ympw/SyKRN3HbmRI/AAAAAAAAA9Y/HAXGyBnTBX4/s400/entity.png](http://lh5.ggpht.com/_alGXTM7ympw/SyKRN3HbmRI/AAAAAAAAA9Y/HAXGyBnTBX4/s400/entity.png)
    * For standard objects, this is usually the name such as `Account` or `Lead`
    * For custom objects, this is usually the name with `__c` such as `CustomObject__c` - You can see the API name for an object on the Object Definition page under Setup within Salesforce.
### 4. Review Results and Create Files ###
> ![http://lh3.ggpht.com/_alGXTM7ympw/SyKo6-yRi7I/AAAAAAAAA9k/COLSrBMHITI/s400/result.png](http://lh3.ggpht.com/_alGXTM7ympw/SyKo6-yRi7I/AAAAAAAAA9k/COLSrBMHITI/s400/result.png)


# Using the Files #
See [UsingCLIqFiles](UsingCLIqFiles.md) for details on configuring and using the files created by CLIq.