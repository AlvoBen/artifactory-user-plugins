﻿Artifactory Before Symbol Server Download User Plugin
 ==========================================

The Artifactory Symbol Server Plugin listens for requests for symbol files and then redirects them to the Microsoft Symbol Server.
For more information on how to use this plugin, please go to: https://www.jfrog.com/confluence/display/RTF/Microsoft+Symbol+Server

### Features
 This plugin adds “User-Agent: Microsoft-Symbol-Server” to http.headers before fetching a symbol file from the Microsoft Symbol Server.

### Installation
 To install this plugin:
   1. Place file beforeSymbolServerDownload.groovy under the Artifactory server `${ARTIFACTORY_HOME}/etc/plugins/`.
   2. Verify in the `${ARTIFACTORY_HOME}/logs/artifactory.log` that the plugin loaded correctly.


 To enable logging for the plugin, add the below logger to your ${ARTIFACTORY.HOME}/etc/ logback.xml:
 ```XML
   <logger name="beforeSymbolServerDownload">
        <level value="debug"/>
   </logger>
   <!-- This logger is necessary for test script running so as to check http-outgoing value of   
    request.headers  -->
   <logger name="org.apache.http.wire">  
      <level value="debug"/>
   </logger>
```

