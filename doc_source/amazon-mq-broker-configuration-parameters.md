# ActiveMQ broker configuration parameters<a name="amazon-mq-broker-configuration-parameters"></a>

A *configuration* contains all of the settings for your ActiveMQ broker, in XML format \(similar to ActiveMQ's `activemq.xml` file\)\. You can create a configuration before creating any brokers\. You can then apply the configuration to one or more brokers\. For more information, see the following:
+ [Configuration](configuration.md)
+ [Creating and applying ActiveMQ broker configurations](amazon-mq-creating-applying-configurations.md)
+ [Editing ActiveMQ broker configurations and managing configuration revisions](amazon-mq-editing-managing-configurations.md)
+ [Configurations](amazon-mq-limits.md#configuration-limits)

## Working with Spring XML configuration files<a name="working-with-spring-xml-configuration-files"></a>

ActiveMQ brokers are configured using [Spring XML](https://docs.spring.io/spring/docs/current/spring-framework-reference/) files\. You can configure many aspects of your ActiveMQ broker, such as predefined destinations, destination policies, authorization policies, and plugins\. Amazon MQ controls some of these configuration elements, such as network transports and storage\. Other configuration options, such as creating networks of brokers, aren't currently supported\.

The full set of supported configuration options is specified in the Amazon MQ XML schemas\. Download zip files of the supported schemas using the following links\.
+  [samples/amazon-mq-active-mq-5.16.3.xsd.zip](samples/amazon-mq-active-mq-5.16.3.xsd.zip) 
+  [samples/amazon-mq-active-mq-5.16.2.xsd.zip](samples/amazon-mq-active-mq-5.16.2.xsd.zip) 
+  [samples/amazon-mq-active-mq-5.15.15.xsd.zip](samples/amazon-mq-active-mq-5.15.15.xsd.zip) 
+  [samples/amazon-mq-active-mq-5.15.14.xsd.zip](samples/amazon-mq-active-mq-5.15.14.xsd.zip) 
+  [samples/amazon-mq-active-mq-5.15.13.xsd.zip](samples/amazon-mq-active-mq-5.15.13.xsd.zip) 
+  [samples/amazon-mq-active-mq-5.15.12.xsd.zip](samples/amazon-mq-active-mq-5.15.12.xsd.zip) 
+ [samples/amazon-mq-active-mq-5.15.10.xsd.zip](samples/amazon-mq-active-mq-5.15.10.xsd.zip)
+ [samples/amazon-mq-active-mq-5.15.9.xsd.zip](samples/amazon-mq-active-mq-5.15.9.xsd.zip)
+ [samples/amazon-mq-active-mq-5.15.8.xsd.zip](samples/amazon-mq-active-mq-5.15.8.xsd.zip)
+ [samples/amazon-mq-active-mq-5.15.6.xsd.zip](samples/amazon-mq-active-mq-5.15.6.xsd.zip)
+ [samples/amazon-mq-active-mq-5.15.0.xsd.zip](samples/amazon-mq-active-mq-5.15.0.xsd.zip)

You can use these schemas to validate and sanitize your configuration files\. Amazon MQ also lets you provide configurations by uploading XML files\. When you upload an XML file, Amazon MQ automatically sanitizes and removes invalid and prohibited configuration parameters according to the schema\.

**Note**  
You can use only static values for attributes\. Amazon MQ sanitizes elements and attributes that contain Spring expressions, variables, and element references from your configuration\.

**Topics**
+ [Working with Spring XML configuration files](#working-with-spring-xml-configuration-files)
+ [Elements Permitted in Amazon MQ Configurations](permitted-elements.md)
+ [Elements and Their Attributes Permitted in Amazon MQ Configurations](permitted-attributes.md)
+ [Elements, Child Collection Elements, and Their Child Elements Permitted in Amazon MQ Configurations](permitted-collections.md)