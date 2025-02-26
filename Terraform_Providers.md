## Terraform Providers

[Terraform Provider](https://developer.hashicorp.com/terraform/language/providers/configuration) allow Terraform to interact with cloud providers, SaaS providers, and other APIs. Some providers require you to configure them with endpoint URLs, cloud regions, or other settings before Terraform can use them. This page documents how to configure settings for providers.

Additionally, all Terraform configurations must declare which providers they require so that Terraform can install and use them.
<br>

## Adding a provider

For  instance, if we want to create/add an AWS provider we can achieve it by doing the following:

copy and past the following code to a filename that we will be createing and call it ```providers.tf```.
```
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
}
```
If the version of the provider was not specified, by default, terraform take it's latest version.
<br>
<br>

Next, we will then execute the command:
```
terraform init
```
<br>

Once this command is executed, it will then download all the code from this particular provider from the [terraform registry](https://registry.terraform.io/). After it is downloaded, we will be now able to create any resources from the aws cloud.
<br>

## Adding multiple providers

You can also add an additional provider on the ```providers.tf``` file. Once you've added the additional provider, make sure to execute ```terraform init```.





