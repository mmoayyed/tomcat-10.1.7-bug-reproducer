## Instructions

You will need JDK 17:

```
openjdk version "17.0.5" 2022-10-18 LTS
OpenJDK Runtime Environment Zulu17.38+21-CA (build 17.0.5+8-LTS)
OpenJDK 64-Bit Server VM Zulu17.38+21-CA (build 17.0.5+8-LTS, mixed mode, sharing)
```

Then run:

```bash
./gradlew clean build
```

Then run the app:

```bash
java -jar build/libs/cas.war --server.ssl.enabled=false --server.port=8080
```

See the error:

```
Caused by: java.lang.NullPointerException: Cannot invoke "java.net.URL.getProtocol()" because "url" is null
    at org.apache.catalina.webresources.StandardRoot$BaseLocation.<init>(StandardRoot.java:815) ~[tomcat-embed-core-10.1.7-SNAPSHOT.jar!/:?]
    at org.apache.catalina.webresources.StandardRoot.createWebResourceSet(StandardRoot.java:357) ~[tomcat-embed-core-10.1.7-SNAPSHOT.jar!/:?]
    at org.apache.catalina.webresources.StandardRoot.processWebInfLib(StandardRoot.java:588) ~[tomcat-embed-core-10.1.7-SNAPSHOT.jar!/:?]
    at org.apache.catalina.webresources.StandardRoot.startInternal(StandardRoot.java:721) ~[tomcat-embed-core-10.1.7-SNAPSHOT.jar!/:?]
    at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:183) ~[tomcat-embed-core-10.1.7-SNAPSHOT.jar!/:?]
    at org.apache.catalina.core.StandardContext.resourcesStart(StandardContext.java:4566) ~[tomcat-embed-core-10.1.7-SNAPSHOT.jar!/:?]
    at org.apache.catalina.core.StandardContext.startInternal(StandardContext.java:4699) ~[tomcat-embed-core-10.1.7-SNAPSHOT.jar!/:?]
    at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:183) ~[tomcat-embed-core-10.1.7-SNAPSHOT.jar!/:?]
    at org.apache.catalina.core.ContainerBase$StartChild.call(ContainerBase.java:1332) ~[tomcat-embed-core-10.1.7-SNAPSHOT.jar!/:?]
    at org.apache.catalina.core.ContainerBase$StartChild.call(ContainerBase.java:1322) ~[tomcat-embed-core-10.1.7-SNAPSHOT.jar!/:?]
    at java.util.concurrent.FutureTask.run(FutureTask.java:264) ~[?:?]
    at org.apache.tomcat.util.threads.InlineExecutorService.execute(InlineExecutorService.java:75) ~[tomcat-embed-core-10.1.7-SNAPSHOT.jar!/:10.1.7-dev]
    at java.util.concurrent.AbstractExecutorService.submit(AbstractExecutorService.java:145) ~[?:?]
    at org.apache.catalina.core.ContainerBase.startInternal(ContainerBase.java:871) ~[tomcat-embed-core-10.1.7-SNAPSHOT.jar!/:?]
    at org.apache.catalina.core.StandardHost.startInternal(StandardHost.java:846) ~[tomcat-embed-core-10.1.7-SNAPSHOT.jar!/:?]
    at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:183) ~[tomcat-embed-core-10.1.7-SNAPSHOT.jar!/:?]
    at org.apache.catalina.core.ContainerBase$StartChild.call(ContainerBase.java:1332) ~[tomcat-embed-core-10.1.7-SNAPSHOT.jar!/:?]
    at org.apache.catalina.core.ContainerBase$StartChild.call(ContainerBase.java:1322) ~[tomcat-embed-core-10.1.7-SNAPSHOT.jar!/:?]
    at java.util.concurrent.FutureTask.run(FutureTask.java:264) ~[?:?]
    at org.apache.tomcat.util.threads.InlineExecutorService.execute(InlineExecutorService.java:75) ~[tomcat-embed-core-10.1.7-SNAPSHOT.jar!/:10.1.7-dev]
    at java.util.concurrent.AbstractExecutorService.submit(AbstractExecutorService.java:145) ~[?:?]
    at org.apache.catalina.core.ContainerBase.startInternal(ContainerBase.java:871) ~[tomcat-embed-core-10.1.7-SNAPSHOT.jar!/:?]
    at org.apache.catalina.core.StandardEngine.startInternal(StandardEngine.java:241) ~[tomcat-embed-core-10.1.7-SNAPSHOT.jar!/:?]
    at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:183) ~[tomcat-embed-core-10.1.7-SNAPSHOT.jar!/:?]
    at org.apache.catalina.core.StandardService.startInternal(StandardService.java:428) ~[tomcat-embed-core-10.1.7-SNAPSHOT.jar!/:?]
    at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:183) ~[tomcat-embed-core-10.1.7-SNAPSHOT.jar!/:?]
    at org.apache.catalina.core.StandardServer.startInternal(StandardServer.java:913) ~[tomcat-embed-core-10.1.7-SNAPSHOT.jar!/:?]
    at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:183) ~[tomcat-embed-core-10.1.7-SNAPSHOT.jar!/:?]
    at org.apache.catalina.startup.Tomcat.start(Tomcat.java:485) ~[tomcat-embed-core-10.1.7-SNAPSHOT.jar!/:?]
    at org.springframework.boot.web.embedded.tomcat.TomcatWebServer.initialize(TomcatWebServer.java:123) ~[spring-boot-3.0.2.jar!/:3.0.2]
    at org.springframework.boot.web.embedded.tomcat.TomcatWebServer.<init>(TomcatWebServer.java:104) ~[spring-boot-3.0.2.jar!/:3.0.2]
    at org.springframework.boot.web.embedded.tomcat.TomcatServletWebServerFactory.getTomcatWebServer(TomcatServletWebServerFactory.java:486) ~[spring-boot-3.0.2.jar!/:3.0.2]
    at org.apereo.cas.tomcat.CasTomcatServletWebServerFactory.getTomcatWebServer(CasTomcatServletWebServerFactory.java:79) ~[cas-server-webapp-init-tomcat-7.0.0-RC4.jar!/:7.0.0-RC4]
    at org.springframework.boot.web.embedded.tomcat.TomcatServletWebServerFactory.getWebServer(TomcatServletWebServerFactory.java:210) ~[spring-boot-3.0.2.jar!/:3.0.2]
    at org.springframework.boot.web.servlet.context.ServletWebServerApplicationContext.createWebServer(ServletWebServerApplicationContext.java:183) ~[spring-boot-3.0.2.jar!/:3.0.2]
    at org.springframework.boot.web.servlet.context.ServletWebServerApplicationContext.onRefresh(ServletWebServerApplicationContext.java:161) ~[spring-boot-3.0.2.jar!/:3.0.2]
    ... 15 more
```     