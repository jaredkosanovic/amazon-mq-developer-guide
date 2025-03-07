# Managing Amazon MQ for RabbitMQ engine versions<a name="rabbitmq-version-management"></a>

 RabbitMQ organizes version numbers according to semantic versioning specification as `X.Y.Z`\. In Amazon MQ for RabbitMQ implementations, `X.Y` denotes the major version, and `Z` represents the minor version number\. Amazon MQ considers a version change to be major if the major version numbers change\.  A version change is considered minor if only the minor version number changes\. For example, upgrading from version 3\.8\.**11** to 3\.8\.**17** is considered a *minor version upgrade*\. 

 Amazon MQ for RabbitMQ currently supports the following engine versions of RabbitMQ\. 


| Major versions | Minor versions | 
| --- | --- | 
| RabbitMQ 3\.8 |  [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/amazon-mq/latest/developer-guide/rabbitmq-version-management.html)  | 

 When you create a new Amazon MQ for RabbitMQ broker, you can specify any supported RabbitMQ engine version\. If you use the AWS Management Console to create a broker, Amazon MQ automatically defaults to the latest engine version number\. If you use the AWS CLI or the Amazon MQ API to create a broker, the engine version number is required\. If you don't provide a version number, the operation will result in an exception\. To learn more, see [https://docs.aws.amazon.com/cli/latest/reference/mq/create-broker](https://docs.aws.amazon.com/cli/latest/reference/mq/create-broker) in the *AWS CLI Command Reference* and [https://docs.aws.amazon.com/amazon-mq/latest/api-reference/brokers.html#CreateBroker](https://docs.aws.amazon.com/amazon-mq/latest/api-reference/brokers.html#CreateBroker) in the *Amazon MQ REST API Reference*\. 

**Topics**
+ [Major and minor version upgrades](#rabbitmq-version-management-upgrading)
+ [Listing supported engine versions](#rabbitmq-version-management-listing-versions)

## Major and minor version upgrades<a name="rabbitmq-version-management-upgrading"></a>

 With Amazon MQ, you control when to upgrade your brokers to new versions\. When [ automatic minor version upgrade](https://docs.aws.amazon.com/amazon-mq/latest/api-reference/brokers-broker-id.html#brokers-broker-id-prop-updatebrokerinput-autominorversionupgrade) is activated, Amazon MQ will automatically upgrade your broker engine to new ActiveMQ minor versions as they are released and supported by Amazon MQ\. 

 To perform a major version upgrade, you must manually upgrade your broker's engine version number\. Minor and major version upgrades occure at the same time as other broker patching operations, during your scheduled [maintenance window](maintaining-brokers.md)\. If you opt out of automatic minor version upgrades, you can manually upgrade your broker to a new supported minor version by following the same procedure as a major upgrade\. 

 For more information about updating your broker preferences to activate or deactivate minor version upgrades, and manually upgrading your broker, see [Upgrading an Amazon MQ broker engine version](upgrading-brokers.md)\. 

**Note**  
Amazon MQ for RabbitMQ supports one major release \(3\.8\.x\), and no major version upgrades are currently available\.

## Listing supported engine versions<a name="rabbitmq-version-management-listing-versions"></a>

 You can list all supported minor and major engine versions by using the [https://docs.aws.amazon.com/cli/latest/reference/mq/describe-broker-instance-options.html](https://docs.aws.amazon.com/cli/latest/reference/mq/describe-broker-instance-options.html) AWS CLI command\. 

```
aws mq describe-broker-instance-options
```

To filter the results by engine and instance type use the `--engine-type` and `--host-instance-type` options as shown in the following\.

```
aws mq describe-broker-instance-options --engine-type engine-type --host-instance-type instance-type
```

For example, to filter the results for RabbitMQ, and `mq.m5.large` instance type, replace *engine\-type* with `RABBITMQ-` and *instance\-type* with `mq.m5.large`\.