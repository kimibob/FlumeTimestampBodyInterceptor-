# FlumeTimestampBodyInterceptor-
在even body中增加时间戳
Install：
1. Check out this code
2. Modify the property in pom.xml to correspond to your version of Flume
3. Build it: mvn clean package
4. Copy the jar generated in the target directory into ${FLUME_HOME}/lib 
    or: ${FLUME_HOME} 
        |-- plugins.d 
          |-- flume-ng-extends-interceptor
            |-- lib 
              |-- flume-ng-extends-source-x.x.x.jar 
            |-- libext
5. vim /conf/flume.conf (or whatever the config file is): 
  a1.sources.r1.interceptors = i1 
  a1.sources.r1.interceptors.i1.type = com.zq.flume.interceptor.TimestampBodyInterceptor$Builder 
  a1.sources.r1.interceptors.i1.separator = ,
6. Restart Flume Agent

a1.sources.r1.interceptors = i1
a1.sources.r1.interceptors.i1.type = com.zq.flume.interceptor.timestampbodyinterceptor.TimestampBodyInterceptor$Builder
a1.sources.r1.interceptors.i1.separator = ,
