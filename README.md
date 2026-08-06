<!-- Copyright IBM Corp. 2014, 2026 -->
<!-- SPDX-License-Identifier: MPL-2.0 -->

<div align="center">

# ☁️ Terraform AWS Provider

### *Enterprise-Grade Infrastructure as Code for Amazon Web Services*

[![Go Version](https://img.shields.io/badge/Go-1.26%2B-00ADD8?style=for-the-badge&logo=go&logoColor=white)](https://go.dev)
[![AWS SDK v2](https://img.shields.io/badge/AWS%20SDK-v2-FF9900?style=for-the-badge&logo=amazon-aws&logoColor=white)](https://aws.amazon.com/sdk-for-go/)
[![License](https://img.shields.io/badge/License-MPL--2.0-blue?style=for-the-badge&logo=open-source-initiative&logoColor=white)](LICENSE)
[![Maintained By](https://img.shields.io/badge/Maintained%20By-VivekGitNinja-24292e?style=for-the-badge&logo=github&logoColor=white)](https://github.com/VivekGitNinja)

---

</div>

## 📌 Overview

The **Terraform AWS Provider** enables developers and platform teams to interact with the vast ecosystem of **Amazon Web Services (AWS)** using declarative Infrastructure as Code (IaC) with [Terraform](https://www.terraform.io/).

This repository is maintained by [**@VivekGitNinja**](https://github.com/VivekGitNinja) and includes comprehensive support for AWS resources, data sources, ephemeral resources, and custom provider actions built on modern Go idioms and dual-framework architecture.

---

## 🔥 Key Features

- **🚀 Dual-Framework Architecture**: Seamlessly combines [Terraform Plugin Framework](https://developer.hashicorp.com/terraform/plugin/framework) (modern) and **SDKv2** via muxing.
- **⚡ AWS SDK for Go v2**: High-performance, low-latency API communication with modern Go 1.26+ features.
- **🛠️ Automated Code Generation**: Code generators (`internal/generate/`) for robust schema management.
- **🛡️ Battle-Tested Reliability**: Built-in exponential backoffs, automatic retries (`internal/retry/`), and rate-limit handling.
- **🌐 Comprehensive AWS Coverage**: Full coverage across compute (EC2, EKS, Lambda), storage (S3, EBS), database (RDS, DynamoDB), security (IAM, WAF, KMS), networking (VPC, Route53), AI/ML (Bedrock, SageMaker), and more.

---

## 💻 Quick Start

### Using the Provider in Terraform

Add the AWS provider to your Terraform configuration:

```hcl
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
}

provider "aws" {
  region = "us-east-1"
}

# Example Resource: S3 Bucket
resource "aws_s3_bucket" "example" {
  bucket = "my-tf-aws-provider-bucket"

  tags = {
    Name        = "My Bucket"
    Environment = "Dev"
    ManagedBy   = "VivekGitNinja"
  }
}
```

---

## 🛠️ Local Development & Building

### Prerequisites
- **Go**: `1.26` or higher installed
- **Terraform**: `1.8.0+` installed
- **GNU Make**

### Build the Provider Binary
To compile the provider binary locally:

```bash
make build
```

### Run Unit Tests
To run unit test suites:

```bash
make test
```

### Format & Lint Code
To verify formatting and run linters:

```bash
make fmt-check
make lint
```

---

## 📁 Repository Structure

```
terraform-provider-aws/
├── .changelog/             # Change log entries for upcoming releases
├── internal/
│   ├── acctest/            # Acceptance testing utilities and helpers
│   ├── conns/              # Global provider context and AWS clients
│   ├── framework/          # Terraform Plugin Framework utilities & validators
│   ├── generate/           # Automated code generators
│   ├── retry/              # Resource retry and wait-for-state mechanisms
│   ├── service/            # Per-service resource & data source implementations
│   └── tags/               # AWS resource tagging logic
├── website/                # Provider documentation and Markdown guides
├── GNUmakefile             # Build, lint, and testing automation
└── main.go                 # Provider executable entry point
```

---

## 👤 Maintainer & Repository Owner

<div align="center">

| Maintainer | GitHub Profile | Repository |
| :--- | :--- | :--- |
| **Vivek** | [@VivekGitNinja](https://github.com/VivekGitNinja) | [VivekGitNinja/Terraform-provider-aws](https://github.com/VivekGitNinja/Terraform-provider-aws) |

</div>

---

## 📄 License

Distributed under the [Mozilla Public License 2.0 (MPL-2.0)](LICENSE).
