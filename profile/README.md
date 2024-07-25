# terraform-aws-mods

This account is for Terraform modules using the [AWSCC provider](https://registry.terraform.io/providers/hashicorp/awscc/latest).

## Coding Standards

Modules will conform to general best practices.  In addition, the following standards will be used which will set them apart from the [terraform-aws-modules](https://github.com/terraform-aws-modules) code:

1. Variable validation - Utilization of  validation to ensure that input variables are of the proper values.  This will reduce the amount of error handling code required within the module logic.  In addition, cross-type references in variables will be used, which requires Terraform 1.9, or higher; the CloudFormation schemas can be leveraged with the `http` provider (see: [aws-cloudformation-schemas](https://github.com/terraform-awscc-mods/aws-cloudformation-schemas))
2. Limited use of `create` bools - There will be no `create_<principal_resource>` variables for conditional creation.  If you don't want to create the resource, don't call the module.
3. No additional *.tf files - Only `main.tf`, `outputs.tf`, and `variables.tf` will be used.
4. Terraform Test - Tests will be utilized to verify the continued operation of code.
