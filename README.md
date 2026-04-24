# helm-charts

[![License](https://img.shields.io/badge/License-MIT-blue)](https://opensource.org/licenses/MIT)

## Usage

[Helm](https://helm.sh) must be installed to use the charts. Please refer to
Helm's [documentation](https://helm.sh/docs) to get started.

Once Helm has been set up correctly, add the repo as follows:

```sh
helm repo add smalinet https://smalinet.github.io/
```

If you had already added this repo earlier, run `helm repo update` to retrieve
the latest versions of the packages. You can then run `helm search repo
smalinet` to see the charts.

To install the <chart_name> chart:

```sh
helm upgrade --install <chart_name> smalinet/<chart_name>
```

Using an OCI-based registry:

```sh
helm upgrade --install <chart_name> oci://ghcr.io/babykart/helm-charts/<chart_name>
 ```

To uninstall the chart:

```sh
helm delete <chart_name>
```
