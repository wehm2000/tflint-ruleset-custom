# TFLint Ruleset Template
[![Build Status](https://github.com/terraform-linters/tflint-ruleset-template/workflows/build/badge.svg?branch=main)](https://github.com/terraform-linters/tflint-ruleset-template/actions)

This is a template repository for building a custom ruleset. You can create a plugin repository from "Use this template". See also [Writing Plugins](https://github.com/terraform-linters/tflint/blob/master/docs/developer-guide/plugins.md).

## Requirements

- TFLint v0.42+
- Go v1.21

## Installation

TODO: This template repository does not contain release binaries, so this installation will not work. Please rewrite for your repository. See the "Building the plugin" section to get this template ruleset working.

You can install the plugin with `tflint --init`. Declare a config in `.tflint.hcl` as follows:

```hcl
plugin "template" {
  enabled = true

  version = "0.1.0"
  source  = "github.com/wehm2000/tflint-ruleset-custom"

  signing_key = <<-KEY
  -----BEGIN PGP PUBLIC KEY BLOCK-----

    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
    =d51z
    -----END PGP PUBLIC KEY BLOCK-----
  KEY
}
```

## Rules

|Name|Description|Severity|Enabled|Link|
| --- | --- | --- | --- | --- |
|aws_instance_example_type|Example rule for accessing and evaluating top-level attributes|ERROR|✔||
|aws_s3_bucket_example_lifecycle_rule|Example rule for accessing top-level/nested blocks and attributes under the blocks|ERROR|✔||
|google_compute_ssl_policy|Example rule with a custom rule config|WARNING|✔||
|terraform_backend_type|Example rule for accessing other than resources|ERROR|✔||

## Building the plugin

Clone the repository locally and run the following command:

```
$ make
```

You can easily install the built plugin with the following:

```
$ make install
```

You can run the built plugin like the following:

```
$ cat << EOS > .tflint.hcl
plugin "template" {
  enabled = true
}
EOS
$ tflint
```
