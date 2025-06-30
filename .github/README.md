# atmos-pro-example-basic


A basic example demonstrating how to use Atmos Pro with GitHub Actions for infrastructure deployment. This repository shows the minimal configuration needed to get started with Atmos Pro workflows.


## Introduction

This is a basic example repository that demonstrates how to use Atmos Pro with GitHub Actions for infrastructure deployment. It provides a minimal setup to help you understand the core concepts of Atmos Pro workflows.

For comprehensive documentation and advanced features, visit [atmos-pro.com/docs](https://atmos-pro.com/docs).



## Usage

### Installation

Before using this example, you'll need to install Atmos. For installation instructions, visit the [Atmos installation guide](https://atmos.tools/install).

### Quick Start

Follow these steps to get started with this Atmos Pro example:

1. **Clone this repository**
   ```bash
   git clone https://github.com/cloudposse-examples/atmos-pro-example-basic.git
   cd atmos-pro-example-basic
   ```

2. **Install Atmos Pro**
   - Follow the [Atmos Pro documentation](https://atmos-pro.com/docs) to install Atmos Pro in this repository.

3. **Set up GitHub Variables**
   - `ATMOS_PRO_WORKSPACE_ID` - Your Atmos Pro workspace ID
   - `ATMOS_VERSION` - The version of Atmos to use (e.g., `1.181.0`)
   - `ATMOS_CONFIG_PATH` - Path to your Atmos configuration file (e.g., `atmos.yaml`)

   For more information about GitHub variables, see the [GitHub documentation](https://docs.github.com/en/actions/how-tos/writing-workflows/choosing-what-your-workflow-does/store-information-in-variables).

4. **Create a pull request**
   - Modify an example component in `stacks/deploy/nonprod.yaml`
     For example, change the value of `foo` from `"nonprod foo"` to `"nonprod foo updated"`
   - Create a pull request on GitHub to trigger the Atmos Pro workflows.

Then let Atmos Pro do the rest!

### How it works

This example demonstrates the minimal configuration needed to use Atmos Pro with GitHub Actions. The workflow follows these steps:

<details>
<summary><strong>On Pull Requests</strong></summary>

When a pull request is created or updated, Atmos Pro triggers [`atmos terraform plan`](.github/workflows/atmos-terraform-plan.yaml):

1. **Developer makes a change** - You modify your infrastructure code
2. **Code is pushed to feature branch** - Changes are committed and pushed
3. **GitHub Actions trigger Atmos affected stacks** - Atmos identifies which stacks are affected by your changes
4. **Atmos uploads affected stacks** - The affected stack configurations are uploaded to Atmos Pro
5. **Atmos Pro dispatches plan workflows** - Atmos Pro automatically runs `atmos terraform plan` for affected components
6. **Atmos Pro updates status comment** - Results are posted as a comment on your pull request

This gives you visibility into what changes will be made to your infrastructure before merging.
</details>

<details>
<summary><strong>On Merged Pull Requests</strong></summary>

When a pull request is merged, Atmos Pro triggers [`atmos terraform apply`](.github/workflows/atmos-terraform-apply.yaml):

1. **Pull request is merged** - Your changes are merged into the main branch
2. **GitHub Actions trigger Atmos affected stacks** - Atmos identifies which stacks need to be updated
3. **Atmos uploads affected stacks** - The affected stack configurations are uploaded to Atmos Pro
4. **Atmos Pro dispatches apply workflows** - Atmos Pro automatically runs `atmos terraform apply` for affected components
5. **Atmos Pro updates status comment** - Deployment results are posted as a comment on the merged PR

This ensures your infrastructure changes are automatically deployed when code is merged.
</details>

For more detailed configuration options and advanced features, refer to the [Atmos Pro documentation](https://atmos-pro.com/docs).

#### Backend Configuration

> **Coming Soon**: Backend configuration will be configured solely with Atmos Pro in the future.

Currently, backend configuration is set in `stacks/deploy/_defaults.yaml`.


### Building Documentation

To build the documentation for this repository, run:

```bash
atmos docs generate readme
```

This command generates the README.md file from the README.yaml configuration.

### Repository Structure

```
.
├── .github/
│   ├── README.md              # Generated README for GitHub
│   ├── README.md.gotmpl       # Template for README generation
│   └── workflows/             # GitHub Actions workflows
│       ├── atmos-pro.yaml     # Main Atmos Pro workflow
│       ├── atmos-terraform-apply.yaml
│       ├── atmos-terraform-plan.yaml
│       └── atmos-validate.yaml
├── README.yaml                # Main documentation source
├── atmos.yaml                 # Atmos configuration
├── components/                # Infrastructure components
│   └── terraform/
│       ├── my-example-component-1/  # Example Terraform component 1
│       │   ├── README.md
│       │   └── main.tf
│       └── my-example-component-2/  # Example Terraform component 2
│           ├── README.md
│           └── main.tf
└── stacks/                    # Atmos stack configurations
    └── deploy/                # Deployment stacks
        ├── _defaults.yaml     # Default stack settings
        ├── nonprod.yaml       # Non-production environment
        └── prod.yaml          # Production environment
```










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
 