# pipeline-as-code
Examples of pipeline as code configurations

Pipeline-as-code allows version controlling the configuration of our pipelines, and easily restore them in case of disaster.

Furthermore, pipeline changes can be reviewed and shared among teams, and we can also easily rollback to a previous good configuration in case of errors.

Different tools use different approaches for pipeline-as-code. 

This repo will cover several different ones.

## GoCD

GoCD supports pipeline definitions using either [JSON](https://github.com/tomzo/gocd-json-config-plugin) or [YAML](https://github.com/tomzo/gocd-yaml-config-plugin). The necessary plugins come pre-installed with the current version of the server.

We simply need to point GoCD to the repo where we store our pipeline configuration files, and it will pick them up and update its internal configuration. To do so browse the GoCD UI (as Administrator) and go to "Admin" -> "Config XML" -> "Edit". Then include the snippet in [`GoCD`](https://github.com/manupaisable/pipeline-as-code/blob/master/GoCD) / [`pipeline_config_repo.xml`](https://github.com/manupaisable/pipeline-as-code/blob/master/GoCD/pipeline_config_repo.xml), update the repo URL and save. 

It can take a couple of minutes for GoCD to pick up the pipeline configuration files. In case of error, you will see a red "Error" box on the top right of the UI. 

**Note**: GoCD does not allow **both** JSON and YAML files in the same repo, need to pick one.

The naming convention for the pipeline configuration files is that they must end with `.gopipeline.json` or `.gocd.yaml`, respectively for JSON and YAML files.

## Jenkins

To do.

## Bamboo

To do.  

## GitLab

To do.
