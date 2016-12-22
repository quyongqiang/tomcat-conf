### add a user
file: tomcat-users.xml
```xml
<role rolename="manager-gui"/>
<role rolename="manager-script"/>
<role rolename="manager-jmx"/>
<role rolename="manager-status"/>
<user username="tomcat" password="s3cret" roles="manager-gui,manager-script,manager-jmx"/>

```

### config access
file:  conf/Catalina/localhost/manager.xml 

```xml
<Context privileged="true" antiResourceLocking="false" 
         docBase="${catalina.home}/webapps/manager">
    <Valve className="org.apache.catalina.valves.RemoteAddrValve" allow="^.*$" />
</Context>
```
