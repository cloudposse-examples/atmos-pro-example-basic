# atmos-pro-example-basic


A basic example demonstrating how to use Atmos Pro with GitHub Actions for infrastructure deployment. This repository shows the minimal configuration needed to get started with Atmos Pro workflows.


## Introduction

This is a basic example repository that demonstrates how to use Atmos Pro with GitHub Actions for infrastructure deployment. It provides a minimal setup to help you understand the core concepts of Atmos Pro workflows.

For comprehensive documentation and advanced features, visit [atmos-pro.com/docs](https://atmos-pro.com/docs).



## Usage

## Basic Workflow

This example demonstrates the minimal configuration needed to use Atmos Pro with GitHub Actions. The workflow is simple:

### 1. Create a Pull Request
When you create a pull request, it automatically triggers the **plan** workflow. This will:
- Run `atmos plan` for all affected components
- Show you what changes will be made to your infrastructure
- Provide feedback in the PR comments

### 2. Merge the Pull Request
When you merge the pull request, it automatically triggers the **apply** workflow. This will:
- Run `atmos apply` for all affected components
- Apply the planned changes to your infrastructure
- Update the deployment status

## Configuration

The minimal configuration includes:
- `atmos.yaml` - Main Atmos configuration file
- `.github/workflows/` - GitHub Actions workflows for plan and apply
- `components/` - Your infrastructure components
- `stacks/` - Stack configurations

## Getting Started

1. Fork this repository
2. Configure your AWS credentials in GitHub Secrets
3. Update the stack configurations in `stacks/` to match your environment
4. Create a pull request to test the plan workflow
5. Merge the PR to trigger the apply workflow

For more detailed configuration options and advanced features, refer to the [Atmos Pro documentation](https://atmos-pro.com/docs).



## Examples

## Example Components

This repository includes example components that demonstrate different infrastructure patterns:

- **vpc** - Basic VPC configuration
- **database** - RDS database setup
- **api** - API service configuration
- **frontend** - Frontend application setup

Each component includes:
- Terraform configuration
- Component metadata
- Dependencies specification

You can modify these components or add your own to match your infrastructure needs.









## Contributing

This project is under active development, and we encourage contributions from our community.

For 🐛 bug reports & feature requests, please use the [issue tracker](https://github.com/cloudposse-examples/atmos-pro-example-basic/issues).

In general, PRs are welcome. We follow the typical "fork-and-pull" Git workflow.
 1. **Fork** the repo on GitHub
 2. **Clone** the project to your own machine
 3. **Commit** changes to your own branch
 4. **Push** your work back up to your fork
 5. Submit a **Pull Request** so that we can review your changes

**NOTE:** Be sure to merge the latest changes from "upstream" before making a pull request!
## License

<a href="https://opensource.org/licenses/Apache-2.0"><img src="https://img.shields.io/badge/License-Apache%202.0-blue.svg?style=for-the-badge" alt="License"></a>

<details>
<summary>Preamble to the Apache License, Version 2.0</summary>
<br/>
<br/>



```text
Licensed to the Apache Software Foundation (ASF) under one
or more contributor license agreements.  See the NOTICE file
distributed with this work for additional information
regarding copyright ownership.  The ASF licenses this file
to you under the Apache License, Version 2.0 (the
"License"); you may not use this file except in compliance
with the License.  You may obtain a copy of the License at

  https://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing,
software distributed under the License is distributed on an
"AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
KIND, either express or implied.  See the License for the
specific language governing permissions and limitations
under the License.
```
</details>


---
Copyright © 2017-2025 [Cloud Posse, LLC](https://cpco.io/copyright)
 