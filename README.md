# IaC Web Server Template

An Infrastructure as Code template for automatically deploying a secure, public-facing Apache web server on a custom AWS VPC.

## 📋 About This Project

Manually setting up cloud infrastructure is time-consuming and prone to error. This project provides a fully automated, reusable template to provision a complete web server environment on AWS.

By running a simple command, you can deploy a foundational web stack that is secure, repeatable, and easy to tear down. It serves as a practical example of IaC principles and a solid baseline for more complex applications.

## ✨ Key Features

This template will automatically create and configure the following resources:

-   ✅ **Custom VPC:** A logically isolated virtual network to house your resources.
-   ✅ **Public Subnet:** A subnet configured to have access to the public internet.
-   ✅ **Internet Gateway & Route Table:** The necessary components to allow traffic to and from the internet.
-   ✅ **Security Group:** A firewall configured to allow inbound traffic on:
    -   Port `22` (SSH)
    -   Port `80` (HTTP)
    -   Port `443` (HTTPS)
-   ✅ **EC2 Instance:** An Ubuntu Server virtual machine.
-   ✅ **Web Server:** Apache2 is automatically installed and enabled on the EC2 instance using a user-data script.
-   ✅ **Static IP Address:** An Elastic IP is provisioned and associated with the instance, so the public IP address never changes.

## 🛠️ Tech Stack

-   **Cloud Provider:** Amazon Web Services (AWS)
-   **Infrastructure as Code Tool:** `[Terraform / AWS CloudFormation / Pulumi / etc.]`
-   **Operating System:** Ubuntu Server 22.04 LTS
-   **Web Server:** Apache2

## 🚀 Getting Started

### Prerequisites

1.  An [AWS Account](https://aws.amazon.com/premiumsupport/knowledge-center/create-and-activate-aws-account/).
2.  AWS CLI configured with your credentials.
3.  `[Terraform / etc.]` installed on your local machine.

### Installation & Deployment

1.  **Clone the repository:**
    ```sh
    git clone [https://github.com/](https://github.com/)[YOUR_USERNAME]/IaC-Web-Server-Template.git
    cd IaC-Web-Server-Template
    ```

2.  **Initialize the configuration:**
    *(This step may vary depending on your tool)*
    ```sh
    [terraform init / appropriate command for your tool]
    ```

3.  **Review and Deploy the infrastructure:**
    ```sh
    [terraform plan]
    [terraform apply]
    ```
    Enter `yes` when prompted to approve the changes.

4.  **Access your web server:**
    After the deployment is complete, the `public_ip` of the EC2 instance will be displayed as an output. You can visit this IP in your browser to see the default Apache page or SSH into the instance.

### Tearing Down

To avoid incurring AWS charges, you can destroy all the created resources with a single command:
```sh
[terraform destroy]
