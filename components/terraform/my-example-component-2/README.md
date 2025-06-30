# My Example Component 2

This is an example Terraform component used for demonstration purposes in the Atmos Pro example repository. It provides a simple configuration with input variables and corresponding outputs to show how Atmos components work.

## Usage

This component is intended for demonstration and learning purposes. It shows how to create a basic Terraform component that can be used with Atmos Pro workflows.

Example stack usage:

```yaml
components:
  terraform:
    my-example-component-2:
      vars:
        stage: "nonprod"
        foo: "example value"
        bar: "example value"
        baz: "example value"
```

## Requirements

No requirements.

## Providers

No providers.

## Modules

No modules.

## Resources

No resources.

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_stage"></a> [stage](#input\_stage) | Environment stage | `string` | `"nonprod"` | no |
| <a name="input_foo"></a> [foo](#input\_foo) | Example variable foo | `string` | `"foo"` | no |
| <a name="input_bar"></a> [bar](#input\_bar) | Example variable bar | `string` | `"bar"` | no |
| <a name="input_baz"></a> [baz](#input\_baz) | Example variable baz | `string` | `"baz"` | no |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_stage"></a> [stage](#output\_stage) | Environment stage |
| <a name="output_foo"></a> [foo](#output\_foo) | Example variable foo |
| <a name="output_bar"></a> [bar](#output\_bar) | Example variable bar |
| <a name="output_baz"></a> [baz](#output\_baz) | Example variable baz |
