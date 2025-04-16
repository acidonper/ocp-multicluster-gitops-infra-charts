# Infrastructure Chart

This Helm Chart includes a set of templates to setting up an Openshift cluster generating the following elements:

* ArgoCD ApplicationSets (Pull mode Apps in ACM)
* ACM Placements

The idea of these objects are linking a Helm Chart installation (infra-chart), defined the path in the values file, to the Openshift Clusters included in every logical environment defined by ACM using the respective label (environment=xx).

## Testing

The file _values-test.yaml_ is key to test all the functionality implement in the chart. By default, the file _value.yaml_ is empty in order to not generate files that could not be necessary in all the Openshift Clusters for every environment.

Please execute the following command in the CI process to test the chart functionality:

```$bash
helm template . -f values-test.yaml
```

## Author

Asier Cidon @RedHat