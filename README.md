# notes-aws-cloudformation
Notes on AWS CloudFormation.


## Stackery
* AWS CloudFormation templates best practices. https://www.stackery.io/blog/aws-cloudformation-templates-best-practices/
* Collection of AWS resources is called a "stack". These resources work together to build application or solution.
* Use existing stacks and customize, stacks are easier to QA
* If you change the logical ID of an existing resource, Cloudformation will delete it and create a new one. Need to specify `DeletePolicy` attribute in template.
* CloudFormation keep track of current state of AWS infrastructure. If you make changes directly with CLI or management console, then resources will be out of sync with snapshot. This discrepency is called *"drift"*. 
