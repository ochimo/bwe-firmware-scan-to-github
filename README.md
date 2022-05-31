# Binwalk Enterprise GitHub Code Scanning Demo

Repository to use for demoing integration of Binwalk Enterprise firmware image analysis with GitHub code scanning results.

This repository is configured to use the upload-sarif.yml action to parse a results.sarif file into Code Scanning alerts when results.sarif is pushed to the repository.

To generate results.sarif, use the Binwalk Enterprise "Centrifuge CLI" to check a firmware image analysis against a security policy.  You can learn more here:

* [Centrifuge CLI](https://github.com/ReFirmLabs/centrifuge-cli)
* [Centrifuge CLI Policy](https://github.com/ReFirmLabs/centrifuge-cli/blob/master/docs/POLICY.md)

For example:

```
centrifuge --outfmt sarif report --ufid=[REPORT ID] check-policy --policy-yaml sarif-policy.yml --report-url [REPORT URL] > results.sarif
git commit -am "Scan results"
git push
```
