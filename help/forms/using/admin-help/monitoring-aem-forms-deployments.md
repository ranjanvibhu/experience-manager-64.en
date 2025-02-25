---
title: Monitoring AEM forms deployments
seo-title: Monitoring AEM forms deployments
description: You can monitor AEM forms deployments from both a system level and an internal level. Learn more about monitoring AEM forms deployments from this document.
seo-description: You can monitor AEM forms deployments from both a system level and an internal level. Learn more about monitoring AEM forms deployments from this document.
uuid: 032b7a93-3069-4ad5-a8c6-4c160f290669
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/maintaining_aem_forms
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: b3e7bca0-5aaf-4f28-bddb-fd7e8ed72ee8
exl-id: d2cd532b-4086-4553-ac26-f311da6d5ca9
---
# Monitoring AEM forms deployments {#monitoring-aem-forms-deployments}

You can monitor AEM forms deployments from both a system level and an internal level. You can use specialist management tools such as HP OpenView, IBM Tivoli, and CA UniCenter and a third-party JMX monitor called *JConsole* to specifically monitor Java activity. Implementation of a monitoring strategy improves availability, reliability, and performance of your AEM forms deployments.

For more information about monitoring AEM forms deployments, see [A technical guide for monitoring AEM forms deployments](https://www.adobe.com/devnet/livecycle/pdfs/lc_monitoring_wp_ue.pdf).

## Monitoring using MBeans {#monitoring-using-mbeans}

AEM forms provides two registered MBeans that provide navigation and statistic information. These are the only MBeans that are supported for integration and inspection:

* **ServiceStatistic:** This MBean provides information about Service name and its version. 
* **OperationStatistic:** This MBean provides the statistic of every forms server’s service. This is where administrators can get information about a particular service such as invocation time, number of errors, and so on.

### ServiceStatisticMbean public interfaces {#servicestatisticmbean-public-interfaces}

These public interfaces of ServiceStatistic MBean can be accessed for testing purposes:

```as3
 public String getServiceId();  
 public int getMajorVersion();  
 public int getMinorVersion();
```

### OperationStatisticMbean public interfaces {#operationstatisticmbean-public-interfaces}

These public interfaces of OperationStatistic MBean can be accessed for testing purposes:

```as3
 // InvocationCount: The number of times the method is invoked.  
 public long getInvocationCount();  
 // InvocationStartTime: The time at which the method started to execute.  
 public long getInvocationStartTime();  
 // InvocationEndTime: The time at which the method finished execution.  
 public long getInvocationEndTime();  
 // InvocationTime: The time taken for the execution of the method.  
 public long getInvocationTime();  
 // LastSamplingDateTime: Convert InvocationStartTime to a formatted string  
 public String getLastSamplingDateTime();  
 // MaxInvocationTime: The maximum time taken for the execution of the method.  
 public long getMaxInvocationTime();  
 // MinInvocationTime: The minimum time taken for the execution of the method.  
 public long getMinInvocationTime();  
 // AverageInvocationTime: the averege execution time taken for the execution of the method.  
 public double getAverageInvocationTime();  
 // ExceptionCount: The number of times the method has thrown an Exception.  
 public long getExceptionCount();  
 // ExceptionMessage: The message of the last exception occurred.  
 public String getExeptionMessage();  
 public void setExceptionMessage(String errorMessage);
```

### MBean Tree & Operation Statistics {#mbean-tree-operation-statistics}

Using a JMX console (JConsole), statistics from OperationStatistic MBean are available. These statistics are MBean's attributes, and can be navigated under the following hierarchy tree:

**MBean tree**

**Adobe Domain Name:** Depends on Application Server. If the Application Server does not define the domain, the default is adobe.com.

**ServiceType:** AdobeService is the name used to list all services.

**AdobeServiceName:** Service Name, or Service ID.

**Version:** Version of the service.

**Operation Statistics**

**Invocation Time:** Time taken for the execution of the method. This does not include the time the request is serialized, transferred from client to server, and deserialized.

**Invocation count:** The number of times the service is invoked.

**Average invocation time:** Average time of all invocations that have executed since the server was started.

**Max invocation time:** The duration of the longest invocation that has executed since the server was started.

**Min invocation time:** The duration of the shortest invocation that has executed since the server was started.

**Exception Count:** Number of invocations that have resulted in failures.

**Exception Message:** The error message of the last exception that occurred.

**Last Sampling Date Time:** The date of the last invocation.

**Time Unit:** Default is millisecond.

To enable JMX monitoring, the application servers typically need some configuration. See your application server documentation for the specifics.

### Examples of how to set up open JMX access {#examples-of-how-to-set-up-open-jmx-access}

**JBoss 4.0.3/4.2.0 - configure the JVM startup**

To view MBeans from JConsole, configure the JBoss application server’s JVM startup parameters. Ensure JBoss is started from the run.bat/sh file.

1. Edit the run.bat file that is located under InstallJBoss/bin.
1. Find the JAVA_OPTS line and add the following:

   ```as3
    -Dcom.sun.management.jmxremote -Dcom.sun.management.jmxremote.port=9088 -Dcom.sun.management.jmxremote.authenticate=false -Dcom.sun.management.jmxremote.ssl=false
   ```

**WebLogic 9.2 /10 - configure the JVM startup**

1. Edit the startWebLogic.bat file that is located under* [WebLogic home]*/user_projects/domains/Adobe_Live_Cycle/bin. 
1. Find the JAVA_OPTS line and add the following:

   ```as3
    -Dcom.sun.management.jmxremote -Dcom.sun.management.jmxremote.port=9088 -Dcom.sun.management.jmxremote.authenticate=false -Dcom.sun.management.jmxremote.ssl=false
   ```

1. Restart WebLogic.

>[!NOTE]
>
>For WebLogic, you can access the MBean using either remote or IIOP.

**Access the MBean remotely**

1. Launch JConsole for new connection and click remote tab.
1. Enter the hostname and port (9088, the number you specify during the start up options of JVM).

**Websphere 6.1 - configure JVM startup**

1. On the admin console (Application server &gt; server1 &gt; Process Definition &gt; JVM), add the following line into the field for Generic JVM Argument:

   ```as3
    -Djavax.management.builder.initial= -Dcom.sun.management.jmxremote
   ```

1. Add or uncomment the following three lines in the /opt/IBM/WebSphere/AppServer/java/jre/lib/management/management.properties file (or &lt;Your Websphere JRE&gt;/ lib/management/management.properties):

   ```as3
    com.sun.management.jmxremote.port=9999 //any port you like, but make sure you use this port when you connect  
    com.sun.management.jmxremote.authenticate=false  
    com.sun.management.jmxremote.ssl=false
   ```

1. Restart WebSphere.
