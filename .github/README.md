# atmos-pro-example-basic


A basic example demonstrating how to use Atmos Pro with GitHub Actions for infrastructure deployment. This repository shows the minimal configuration needed to get started with Atmos Pro workflows.


## Introduction

This is a basic example repository that demonstrates how to use Atmos Pro with GitHub Actions for infrastructure deployment. It provides a minimal setup to help you understand the core concepts of Atmos Pro workflows.

For comprehensive documentation and advanced features, visit [atmos-pro.com/docs](https://atmos-pro.com/docs).



## Usage

This example demonstrates the minimal configuration needed to use Atmos Pro with GitHub Actions. The workflow follows these steps:

<details>
<summary><strong>On Pull Requests</strong></summary>

When a pull request is created or updated, Atmos Pro triggers `atmos terraform plan`:

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

When a pull request is merged, Atmos Pro triggers `atmos terraform apply`:

1. **Pull request is merged** - Your changes are merged into the main branch
2. **GitHub Actions trigger Atmos affected stacks** - Atmos identifies which stacks need to be updated
3. **Atmos uploads affected stacks** - The affected stack configurations are uploaded to Atmos Pro
4. **Atmos Pro dispatches apply workflows** - Atmos Pro automatically runs `atmos terraform apply` for affected components
5. **Atmos Pro updates status comment** - Deployment results are posted as a comment on the merged PR

This ensures your infrastructure changes are automatically deployed when code is merged.
</details>

<details>
<summary><strong>Configuration</strong></summary>

The minimal configuration includes:
- `atmos.yaml` - Main Atmos configuration file
- `.github/workflows/` - GitHub Actions workflows for plan and apply
- `components/` - Your infrastructure components (Terraform root modules)
- `stacks/` - Atmos stack configurations
</details>

<details>
<summary><strong>Required GitHub Variables</strong></summary>

You'll need to configure the following GitHub variables in your repository settings:

- `ATMOS_PRO_WORKSPACE_ID` - Your Atmos Pro workspace ID
- `ATMOS_VERSION` - The version of Atmos to use (e.g., `1.181.0`)
- `ATMOS_CONFIG_PATH` - Path to your Atmos configuration file (e.g., `atmos.yaml`)
</details>

For more detailed configuration options and advanced features, refer to the [Atmos Pro documentation](https://atmos-pro.com/docs).










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
 