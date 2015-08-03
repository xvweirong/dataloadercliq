# On Windows 7, I get an error "Access is Denied" when creating the files #
A workaround is to turn of the Window 7 User Account Control.

# I get an Error as soon as a run cliq.bat #
On launching, CLIq tries to connect to the Internet (to check for later versions).  If this fails, you will see an error.  Most commonly, it could fail because:
  1. You are not connected to the Internet (which is needed anyway for verifying information with Salesforce)
  1. You are behind a proxy server.  Configure your proxy settings in cliq.properties and restart CLIq.

# I get an Exception when verifying my username/password #
```
Loading GUI...
Exception occurred during event dispatching:
java.lang.NoClassDefFoundError: com/salesforce/dataloader/security/EncryptionUtil
        at com.salesforce.cliq.CliConfig.encryptPassword(CliConfig.java:239)
        at com.salesforce.cliq.CliConfig.setPassword(CliConfig.java:255)
```

This is probably because your version of CLIq does not match your Data Loader version.  (The imported package for encrypting the password is only in version 17.0 and later)

# No X11 DISPLAY variable was set, but this program performed an operation which requires it. #
On UNIX/Linux if you are running from a terminal with no X Windows environment, run CLIq in text mode using:
```
./cliq.sh -t
```

# Error while calling web service operation: describeSObject, error was: Unexpected element #
This error occurs when using a newer version of CLIq (18.0) with an older Data Loader (usually 17.0).  Upgrade your Data Loader and the error should go away.

# When I run the Data Loader process, nothing happens. #
Look in the log directory for the sdl.log file.  This file has all of the console messages from Data Loader, and will probably contain the error causing your problem.

# My export script runs successfully, however the output file only has the field headers without any data.  I know there is data in the object #
Make sure you are not using aliases in your SOQL.
```
Select a.Id from Account a
```
will not work in Data Loader.  Use:
```
Select Id from Account
```
instead.