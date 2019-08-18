# Kubeval

A [GitHub Action](https://github.com/features/actions) for using [Kubeval](https://github.com/instrumenta/kubeval) in your workflows.

You can use the action as follows:

```yaml
on: push
name: Validate
jobs:
  kubeval:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@master
    - name: test
      uses: instrumenta/kubeval-action@master
```

By default the action will recursively scan for YAML files and validate them as Kubernetes obejcts. You can configure this with the parameters.

The Kubeval Action has a number of properties which map to the parameters for Kubeval itself. These are
passed to the action using `with`.

| Property | Default | Description |
| --- | --- | --- |
| files | . | Which files or directories to validate |
| output | stdout | How to format the output from Conftest (stdout, json or tap) |
| openshift | false | Whether or not to use the OpenShift schemas rather than the upstread Kubernetes ones |
| strict | true | Whether ot not to fail for additional properties in objects |
| ignore_missing_schemas | true | Whether to fail if unknown resources are found |
| version | master | Which version of Kubernetes to validate against |

