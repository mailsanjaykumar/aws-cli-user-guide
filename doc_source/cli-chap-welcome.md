# What is the AWS Command Line Interface?<a name="cli-chap-welcome"></a>

The AWS Command Line Interface \(AWS CLI\) is an open source tool that enables you to interact with AWS services using commands in your command\-line shell\. With minimal configuration, the AWS CLI enables you to start running commands that implement functionality equivalent to that provided by the browser\-based AWS Management Console from the command prompt in your terminal program:
+ **Linux shells** – Use common shell programs such as [https://www.gnu.org/software/bash/](https://www.gnu.org/software/bash/), [http://www.zsh.org/](http://www.zsh.org/), and [https://www.tcsh.org/](https://www.tcsh.org/) to run commands in Linux or macOS\.
+ **Windows command line** – On Windows, run commands at the Windows command prompt or in PowerShell\.
+ **Remotely** – Run commands on Amazon Elastic Compute Cloud \(Amazon EC2\) instances through a remote terminal program such as PuTTY or SSH, or with AWS Systems Manager\.

All IaaS \(infrastructure as a service\) AWS administration, management, and access functions in the AWS Management Console are available in the AWS API and CLI\. New AWS IaaS features and services provide full AWS Management Console functionality through the API and CLI at launch or within 180 days of launch\. 

The AWS CLI provides direct access to the public APIs of AWS services\. You can explore a service's capabilities with the AWS CLI, and develop shell scripts to manage your resources\. In addition to the low\-level, API\-equivalent commands, several AWS services provide customizations for the AWS CLI\. Customizations can include higher\-level commands that simplify using a service with a complex API\.

## AWS CLI versions<a name="welcome-versions"></a>

The AWS CLI is available in two versions and information in this guide applies to both versions unless stated otherwise\.
+ **Version 2\.x** – The current, generally available release of the AWS CLI that is intended for use in production environments\. This version does include some "breaking" changes from version 1 that might require you to change your scripts so that they continue to operate as you expect\. For a list of new features and breaking changes in version 2, see [Breaking changes – Migrating from AWS CLI version 1 to version 2](cliv2-migration.md)\.
+ **Version 1\.x** – The previous version of the AWS CLI that is available for backwards compatiblity\.

## Maintenance and support for SDK major versions<a name="sdks-major-versions-maintenance-support"></a>

For information about maintenance and support for SDK major versions and their underlying dependencies, see the following in the [AWS SDKs and Tools Shared Configuration and Credentials Reference Guide](https://docs.aws.amazon.com/credref/latest/refdocs/overview.html):
+ [AWS SDKs and Tools Maintenance Policy](https://docs.aws.amazon.com/credref/latest/refdocs/maint-policy.html)
+ [AWS SDKs and Tools Version Support Matrix](https://docs.aws.amazon.com/credref/latest/refdocs/version-support-matrix.html)

## Additional documentation and resources<a name="welcome-links"></a>

In addition to this guide, the following are valuable online resources for the AWS CLI\.
+ [AWS CLI version 1 reference guide](https://docs.aws.amazon.com/cli/latest/reference/)
+ [AWS CLI version 2 reference guide](https://awscli.amazonaws.com/v2/documentation/api/latest/index.html)
+ [AWS CLI GitHub Repository](https://github.com/aws/aws-cli) You can view—and fork—the source code for the AWS CLI on GitHub in the [aws\-cli repository](https://github.com/aws/aws-cli)\. Join the community of users on GitHub to provide feedback, request features, and submit your own contributions\!
+ [AWS CLI version 1 change notes](https://github.com/aws/aws-cli/blob/develop/CHANGELOG.rst)
+ [AWS CLI version 2 change notes](https://github.com/aws/aws-cli/blob/v2/CHANGELOG.rst)
+ [AWS CLI code examples repository](https://github.com/awsdocs/aws-doc-sdk-examples/tree/master/aws-cli)

### AWS SDKs<a name="cli-sdks"></a>

Depending on your use case, you might want to choose one of the AWS SDKs or the AWS Tools for PowerShell:
+ [AWS Tools for PowerShell](https://docs.aws.amazon.com/powershell/latest/userguide/)
+ [AWS SDK for Java](https://docs.aws.amazon.com/sdk-for-java/v1/developer-guide/)
+ [AWS SDK for \.NET](https://docs.aws.amazon.com/sdk-for-net/latest/developer-guide/)
+ [AWS SDK for JavaScript](https://docs.aws.amazon.com/sdk-for-javascript/v2/developer-guide/)
+ [AWS SDK for Ruby](https://docs.aws.amazon.com/sdk-for-ruby/v3/developer-guide/)
+ [AWS SDK for Python \(Boto\)](http://boto3.amazonaws.com/v1/documentation/api/latest/index.html)
+ [AWS SDK for PHP](https://docs.aws.amazon.com/aws-sdk-php/guide/latest/)
+ [AWS SDK for Go](https://docs.aws.amazon.com/sdk-for-go/api/)
+ [AWS Mobile SDK for iOS](https://docs.aws.amazon.com/mobile/sdkforios/developerguide/)
+ [AWS Mobile SDK for Android](https://docs.aws.amazon.com/mobile/sdkforandroid/developerguide/)

## Using the examples<a name="cli-using-examples"></a>

The examples in this guide are formatted using the following conventions:
+ **Prompt** – The command prompt is displayed as \(`$ `\)\. For commands that are Windows specific, `C:\>` is used as the prompt\. Do not include the prompt when you type commands\. 
+ **Directory** – When commands must be executed from a specific directory, the directory name is shown before the prompt symbol\.
+ **User input** – Command text that you enter at the command line is formatted as **user input**\.
+ **Replaceable text** – Variable text, including names of resources that you choose, or IDs generated by AWS services that you must include in commands, is formatted as *replaceable text*\. In multiple\-line commands or commands where specific keyboard input is required, keyboard commands can also be shown as replaceable text\.
+ **Output** – Output returned by AWS services is shown under user input, and is formatted as computer output\.

For example, the following command includes user input, replaceable text, and output\. To use this example, enter **aws configure** at the command line, and then press **Enter**\. The AWS CLI outputs lines of text, prompting you to enter additional information\. Enter each of your access keys in turn, and then press **Enter**\. Then, enter an AWS Region name in the format shown, press **Enter**, and then press **Enter** a final time to skip the output format setting\. The final **Enter** command is shown as replaceable text because there is no user input for that line\.

```
$ aws configure
AWS Access Key ID [None]: AKIAIOSFODNN7EXAMPLE
AWS Secret Access Key [None]: wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
Default region name [None]: us-west-2
Default output format [None]: ENTER
```

The following example shows a simple command with output\. To use this example, enter the full text of the command \(the highlighted text after the prompt\), and then press **Enter**\. The name of the security group, *`my-sg`*, is replaceable to your desired security group name\. The JSON document, including the curly braces, is output\. If you configure your CLI to output in text or table format, the output will be formatted differently\. [JSON](https://json.org) is the default output format\.

```
$ aws ec2 create-security-group --group-name my-sg --description "My security group"
{
    "GroupId": "sg-903004f8"
}
```

**Note**  
Arguments that must be replaced \(such as AWS Access Key ID\), and those that should be replaced \(such as group name\), are both shown as *replaceable text in italics*\. If an argument must be replaced, it's noted in the text that describes the example\.

## About Amazon Web Services<a name="about-aws"></a>

Amazon Web Services \(AWS\) is a collection of digital infrastructure services that developers can leverage when developing their applications\. The services include computing, storage, database, and application synchronization \(messaging and queuing\)\. AWS uses a pay\-as\-you\-go service model\. You are charged only for the services that you—or your applications—use\. Also, to make AWS more approachable as a platform for prototyping and experimentation, AWS offers a free usage tier\. On this tier, services are free below a certain level of usage\. For more information about AWS costs and the Free Tier, see [Test\-Driving AWS in the Free Usage Tier](https://docs.aws.amazon.com/FeaturedArticles/latest/TestDriveFreeTier.html)\. To obtain an AWS account, open the [AWS home page](https://portal.aws.amazon.com/gp/aws/developer/registration/index.html) and then click **Sign Up**\.