# Introduction #
If you want to modify CLIq for your own use, fix bugs, or just see how it works, you can build your own copy of CLIq.

These instructions assume you have installed:
  * svn
  * JDK >= 1.5
  * ant

# Instructions #
  1. Checkout the code
```
svn checkout http://dataloadercliq.googlecode.com/svn/trunk/ dataloadercliq-read-only
```
  1. Go to the build directory
```
cd dataloadercliq-read-only
```
  1. Copy your DataLoader.jar file into the directory.  It should look like this:
```
vswamidass-ltm:dataloadercliq-read-only vswamidass$ ls
DataLoader.jar	build.xml		lib		src
```
  1. Run the ant target
```
ant build
```
  1. Now you can go to the cliq directory and run cliq
```
cd cliq
./cliq.sh
```

That's it - you can make changes to the code in the src directory, build it, and try it out!