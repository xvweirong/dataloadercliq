**This has been tested on Apple OS X and Linux.  Your feedback from testing on other platforms is appreciated!**

# Requirements #
  * Windows PC (or access to one) to get the `DataLoader.jar` archive.
  * java 1.5 or greater must be in the PATH - This should run successfully:
```
vijay-swamidasss-imac:cliq vijayswamidass$ java -version
java version "1.6.0_17"
Java(TM) SE Runtime Environment (build 1.6.0_17-b04-248-10M3025)
Java HotSpot(TM) 64-Bit Server VM (build 14.3-b01-101, mixed mode)
```


# Instructions #
  1. Download and install Salesforce Data Loader on a Windows PC, and copy the jar file to your UNIX machine.
```
C:\Program Files\salesforce.com\Apex Data Loader 23.0\DataLoader.jar
-or-
C:\Program Files\salesforce.com\Data Loader\dataloader-24.0.0-jar-with-dependencies.jar
```
  1. On your UNIX machine, create a directory for dataloader
```
vijay-swamidasss-imac:~ vijayswamidass$ mkdir /Users/vijayswamidass/dataloader
```
  1. Copy `DataLoader.jar` (from step #1) to the dataloader directory
  1. [Download and install CLIq](http://code.google.com/p/dataloadercliq/wiki/Installation) into the dataloader directory.  You should see:
```
vijay-swamidasss-imac:dataloader vijayswamidass$ pwd
/Users/vijayswamidass/dataloader
vijay-swamidasss-imac:dataloader vijayswamidass$ ls
DataLoader.jar	cliq
```
  1. Change to the cliq directory:
```
vijay-swamidasss-imac:dataloader vijayswamidass$ cd cliq
```
  1. Run CLIq:
```
vijay-swamidasss-imac:cliq vijayswamidass$ ./cliq.sh
Loading GUI...
```

You are now running CLIq on UNIX!  See [UsingCLIq](UsingCLIq.md) for help using CLIq.