# FlumeTimestampBodyInterceptor-
## 在even body中增加时间戳
###Install：
* Check out this code
*  Modify the property in pom.xml to correspond to your version of Flume
*  Build it: mvn clean package
*  Copy the jar generated in the target directory into ${FLUME_HOME}/lib OR: 
```
    ${FLUME_HOME} 
        |-- plugins.d 
          |-- flume-body-timestamp-interceptor
            |-- lib 
              |-- FlumeTimestampBodyInterceptor-x.x.x-SNAPSHOT.jar
            |-- libext
```
*  vim /conf/flume.conf (or whatever the config file is) 
```
  a1.sources.r1.interceptors = i1 
  a1.sources.r1.interceptors.i1.type = com.zq.flume.interceptor.TimestampBodyInterceptor$Builder 
  a1.sources.r1.interceptors.i1.separator = ,
```
*  Restart Flume Agent


