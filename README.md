# CodeCommit to CodeDeploy Buildspec

This repository contains the Buildspec file used to deploy infrastructure using AWS CodeDeploy after changes are pushed to AWS CodeCommit.

## Buildspec Configuration

The Buildspec file defines the different phases of the build process. Here is an overview of the configuration:

# Phases
install: This phase installs Terraform and sets the runtime version to 0.15.x. It downloads the Terraform binary, extracts it, and moves it to the /usr/local/bin/ directory.
build: In this phase, the Terraform commands are executed. It initializes Terraform using terraform init and applies the infrastructure changes using terraform apply -auto-approve.
post_build: After the build phase completes, this phase executes the post-build tasks. In this example, it simply outputs a completion message.

# Usage
To use this Buildspec file, follow these steps:

Create an AWS CodeDeploy application and deployment group.
Set up a CodePipeline or another mechanism to trigger the CodeDeploy deployment on changes to AWS CodeCommit.
Include this Buildspec file in your CodeCommit repository.
Customize the Terraform version and commands as per your requirements.
