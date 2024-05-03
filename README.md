# Terraform Infrastructure Automations
This repository contains all the terraform scripts I've created while learning Terraform specifically focusing on IaC templates for various AWS deployments

## Terraform Commands and Parameters

### Common Commands

- `terraform init`: Initialize a Terraform working directory. This command downloads provider plugins and modules specified in the configuration files. It's typically the first command to run in a new Terraform project or when you add new dependencies.

- `terraform plan`: Generate an execution plan based on your Terraform configuration. This command compares the current state of your infrastructure with the desired state specified in the configuration files. It shows what actions Terraform will take when you apply the configuration.

- `terraform apply`: Apply the changes described in your Terraform execution plan. This command creates, updates, or deletes resources as necessary to match the desired state defined in your configuration files. It's used to make changes to your infrastructure.

- `terraform destroy`: Destroy all resources managed by Terraform in the current working directory. This command removes all resources defined in your Terraform configuration, effectively tearing down your infrastructure. Use with caution as it's irreversible.

### Common Parameters

- `-var`: Set a variable inline with the CLI. This parameter allows you to override variable values specified in your configuration files. For example:
  ```terraform apply -var="region=us-west-2"```
- `-var-file`: Specify a file containing variable definitions. This parameter is useful for separating sensitive information like access keys or passwords from your configuration files. For example:
```terraform apply -var-file="variables.tfvars"```
- `-state`: Specify the path to the Terraform state file. This parameter is handy when working with remote state or when managing multiple Terraform states. For example:
```terraform apply -state="path/to/terraform.tfstate"```
- `-target`: Apply changes only to the specified resource. This parameter allows you to selectively apply changes to a specific resource, which can be helpful when making targeted updates or troubleshooting. For example:
```terraform apply -target=aws_instance.example```
- `auto-approve`: Automatically approve and apply changes without prompting for confirmation. This parameter is useful in automated workflows, such as CI/CD pipelines, where user interaction isn't possible. For example:
```terraform apply -auto-approve```
- `-input=false`: Disable interactive input. This parameter is suitable for non-interactive environments like CI/CD pipelines, where Terraform commands are executed automatically. For example:
```terraform apply -input=false```
- `parallelism`: Limit the number of concurrent operations. This parameter controls the number of resources Terraform creates or destroys simultaneously. It's useful for controlling resource creation or destruction speed, especially when working with large infrastructures. For example:
```terraform apply -parallelism=10```

