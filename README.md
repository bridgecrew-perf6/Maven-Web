### Steps
1. configure in conf folder, file tomcat-user.xml (at every End after)
   ```xml
   <role rolename="manager-gui"/>
   <role rolename="manager-script"/>
   <user username="admin" password="admin" roles="manager-gui,manager-script"/>
  ```
2. set java_home env varaible..
3. Start Tomcat Server 
    * Open Apache tomcat bin folder
    * open cmd here and type just **startup**
    * Change port in port=8080/9090
4. Start Jenkins username/paswrod
5. create new Job give name, select type 1st option -> **freestyle Project**
6. Job Configuration
    * give desc
    * Set git URI
    * Set Build Triggers -> Poll SCM (type * * * * *) 
    * Build 
        - Maven Version - Maven
        - goals - clean package
        - POM - MyWeb/pom.xml  (Name of <Application/pom.xml>)
    * Post-Build Actions
        - war/ear files - **/*.war
        - Context path - MyWeb (Your <Application-name>)
        - Containers - clk -> Add -> username- admin , password -admin ==> then save
        - Tomcat URL - type "http://localhost:8080/"
    * Save
7. click **Build now**
8. If Success, type in new Tab : "http://localhost:8080/MyWeb/"
