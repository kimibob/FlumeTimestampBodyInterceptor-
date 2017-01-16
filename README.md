# FlumeTimestampBodyInterceptor-
## 在even body中增加时间戳
###Install：
1. Check out this code
2. Modify the property in pom.xml to correspond to your version of Flume
3. Build it: mvn clean package
4. Copy the jar generated in the target directory into ${FLUME_HOME}/lib OR: 
```
    ${FLUME_HOME} 
        |-- plugins.d 
          |-- flume-body-timestamp-interceptor
            |-- lib 
              |-- FlumeTimestampBodyInterceptor-x.x.x-SNAPSHOT.jar
            |-- libext
```
5. vim /conf/flume.conf (or whatever the config file is): 
```
  a1.sources.r1.interceptors = i1 
  a1.sources.r1.interceptors.i1.type = com.zq.flume.interceptor.TimestampBodyInterceptor$Builder 
  a1.sources.r1.interceptors.i1.separator = ,
```
6. Restart Flume Agent


