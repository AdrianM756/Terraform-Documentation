## HashiCorp Configuration Language(HCL)

**HashiCorp Configuration Language(HCL)** is a declarative language used to define the infrastructure resources to be provisioned as block of codes. It can be defined within a configuration file with a ```.tf``` file extension.

## Resource

Every object that terraform manages is called [Resource](https://developer.hashicorp.com/terraform/language/resources). It can be a file, virtual machine, services, and many more.

## HCL Basics

An HCL file is consist of **blocks** and **arguments**. **blocks** is defined within curly braces ```{}``` and contains a set of **arguments** in a ```key:value pair``` format. 

Let's create our first HCL file. Inside our Ubuntu machine. create a directory named ```terraform-local-file``` and go inside the directory.

```
mkdir terraform-local-file
```
```
cd terraform-local-file
```
<br>

Next, let's create a file called ```local.tf```.
```
touch local.tf
```
<br>

Inside the ```local.tf``` copy and paste the following:

```
resource "local_file" "First-Terraform-File" {
  filename = "first_Terraform.txt"
  content = "Congratulations on your first Terraform"
}
```
<br>

With the configuration file ready, we can now create the file resource commands as follows. First, we run the command:
```
terraform init
```
The ```terraform init``` command will check the configuration file and initialize the working directory that contains the ```.tf``` file.

<br>

To check the execution plan that terraform will use, we can use the command:
```
terraform plan
```
<br>

After the review, we can now create the resource using the command:
```
terraform apply
```
<br>

It will then prompt and ask the user to confirm by typing ```yes```.








