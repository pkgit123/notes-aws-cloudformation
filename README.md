# notes-aws-cloudformation
Notes on AWS CloudFormation.


## Stackery
1. AWS CloudFormation templates best practices. https://www.stackery.io/blog/aws-cloudformation-templates-best-practices/
2. Collection of AWS resources is called a "stack". These resources work together to build application or solution. Use existing stacks and customize. Stacks are easier to QA
3. If you change the logical ID of an existing resource, Cloudformation will delete it and create a new one. Need to specify `DeletePolicy` attribute in template.
4. CloudFormation keep track of current state of AWS infrastructure. If you make changes directly with CLI or management console, then resources will be out of sync with snapshot. This discrepency is called **"drift"**. 
5. CF Templates are YAML or JSON.
6. Here are 9 sections of template:
    * Description
    * Metadata
    * Parameters. Best practice to store parameters in AWS Systems Manager Parameter Store.
    * Mappings. Logic, e.g. input value as condition.
    * Transform. Specify macros for template reuse. Specify SAM for serverless stacks.
    * Resources.
    * Output. Could be passed to other stacks.
7. Best practices:
   * Store credentials in AWS Secrets Manager
   * Reference non-confidential parameters (e.g. memory size) in AWS Systems Manager Parameter Store.
   * Use YAML syntax shortcuts. (e.g. !GetAtt instead of the full Fn::GetAtt syntax)
   * Add comments and background information.
   * Check code with AWS CloudFormation, cfn-guard, and cfn-nag.
8. CloudFormation sample templates
   * https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/sample-templates-services-us-west-2.html
   * https://s3.us-west-2.amazonaws.com/cloudformation-templates-us-west-2/LAMP_Single_Instance.template
   * https://s3.us-west-2.amazonaws.com/cloudformation-templates-us-west-2/Rails_Single_Instance.template
   * https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/sample-templates-appframeworks-us-west-2.html
   * https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/CHAP_TemplateQuickRef.html
   * https://aws.amazon.com/cloudformation/resources/templates/

## AWS CloudFormation documentation on validating a template
* https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-validate-template.html

## cfn-nag
* https://github.com/stelligent/cfn_nag

## Examples using AWS CloudShell (AWS CLI in Management Console)

```
aws cloudformation validate-template --template-url https://s3.us-west-2.amazonaws.com/cloudformation-templates-us-west-2/AutoScalingMultiAZWithNotifications.template
```
