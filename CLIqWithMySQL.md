# Introduction #
Explains how to use a MySQL database as the datasource for a Data Loader insert into salesforce.com.

Feel free to comment with any feedback or questions.

# Details #

  1. Download the MySQL connector http://www.mysql.com/downloads/connector/j/.  Extract the jar file to the Data Loader home directory (the same dir as DataLoader.jar).
  1. Create an insert process using CLIq.  For this example, I will refer to the process as _my\_process_
  1. Change to the cliq\_process/my\_process directory
  1. Create the file database-conf.xml with these contents, specifying the appropriate parameters for your installation:
```
<!DOCTYPE beans PUBLIC "-//SPRING//DTD BEAN//EN" "http://www.springframework.org/dtd/spring-beans.dtd">
<beans>
<bean id="dbDataSource"
      class="org.apache.commons.dbcp.BasicDataSource"
      destroy-method="close">
    <property name="driverClassName" value="com.mysql.jdbc.Driver"/>
    <property name="url" value="jdbc:mysql://{MYSQL HOSTNAME}/{DATABASE NAME}"/>
    <property name="username" value="{YOUR MYSQL USERNAME}"/>
    <property name="password" value="{YOUR MYSQL PASSWORD}"/>
</bean>
<bean id="queryData"
      class="com.salesforce.dataloader.dao.database.DatabaseConfig"
      singleton="true">
    <property name="sqlConfig" ref="queryDataSql"/>
    <property name="dataSource" ref="dbDataSource"/>
</bean>
<bean id="queryDataSql"
      class="com.salesforce.dataloader.dao.database.SqlConfig" singleton="true">
    <property name="sqlString">
        <value>
{YOUR MYSQL SQL QUERY}
        </value>
    </property>
    <property name="columnNames">
        <list>
            <value>{SQL COLUMN1}</value>
            <value>{SQL COLUMN2}</value>
        </list>
    </property>
</bean>
</beans>
```
  1. Edit the process-conf.xml and set the dataAccess.name and dataAccess.type as follows:
```
<entry key="dataAccess.name" value="queryData"/>
<entry key="dataAccess.type" value="databaseRead"/>
```
  1. Edit my\_process.sh and add the mysql connector to the path:
```
replace 

java -cp $DLPATH/DataLoader.jar 
-Dsalesforce.config.dir=$DLCONF com.salesforce.dataloader.process.ProcessRunner process.name=my_process

with

java -cp $DLPATH/DataLoader.jar:$DLPATH/mysql-connector-java-5.1.16-bin.jar 
-Dsalesforce.config.dir=$DLCONF com.salesforce.dataloader.process.ProcessRunner process.name=my_process
```
  1. On Windows, edit my\_process.bat and add the mysql connector to the path:
```
replace

call %DLPATH%\_jvm\bin\java.exe -cp %DLPATH%\DataLoader.jar 
-Dsalesforce.config.dir=%DLCONF% com.salesforce.dataloader.process.ProcessRunner process.name=my_process

with

call %DLPATH%\_jvm\bin\java.exe -cp %DLPATH%\DataLoader.jar:%DLPATH%\mysql-connector-java-5.1.16-bin.jar 
-Dsalesforce.config.dir=%DLCONF% com.salesforce.dataloader.process.ProcessRunner process.name=my_process
```
  1. Update my\_process.sdl to map the fields from database-conf.xml to salesforce.com API fields.
  1. Run my\_process.sh or my\_process.bat and enjoy!

NOTES
  * SQL COLUMN1, SQL COLUMN2, etc. must match the column names from the SQL query exactly