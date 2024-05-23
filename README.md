# template-terraform-module

This repository is a template for creating a new Terraform module.

## Usage

Clone as a new repository (using the GitHub CLI):

```bash
name="s3-bucket" # Example for naming as 'terraform-aws-s3-bucket'
PUBLIC_REPO="true
TERRAFORM_MODULE_PROVIDER="aws"
TERRAFORM_MODULE_NAME="terraform-${TERRAFORM_MODULE_PROVIDER}-${name}"
TEMPLATE_REPOSITORY="dustindortch/template-terraform-module"

if [ "${PWD##*/}" != "${TERRAFORM_MODULE_NAME}" ]; then
  mkdir -p "${TERRAFORM_MODULE_NAME}"
  cd "${TERRAFORM_MODULE_NAME}"
fi

gh create repo $TERRAFORM_MODULE_NAME $(("${PUBLIC_REPO}" == "true" ? "--public" : "--private")) --template="${TEMPLATE_REPOSITORY}" --clone
```

Modify the name within this README.md file to match the name of the module you are creating (e.g. `terraform-aws-s3-bucket`).

Update the code within the Terraform configuration files (`main.tf`, `variables.tf`, `outputs.tf`) to match the desired functionality of the module.  The files created represent the recommended files for any Terraform configuration code.

<!-- BEGIN_TF_DOCS -->
## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_terraform"></a> [terraform](#requirement\_terraform) | ~> 1.8 |

## Providers

No providers.

## Modules

No modules.

## Resources

No resources.

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_name"></a> [name](#input\_name) | Name of the principal resource for the module. (Required) | `string` | n/a | yes |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_name"></a> [name](#output\_name) | The `name` of the principal resource for the module. |
<!-- END_TF_DOCS -->