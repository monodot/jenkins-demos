# environment-variables

Demonstrations of how Jenkins handles environment variables, because at first glance it seems to be **COMPLETELY AND UTTERLY BONKERS**.

## Jenkinsfile.with-agents

Demonstrating how variables can be shared/propagated across pipeline stages, each of which may run on a different agent or slave node.

To demo (on OpenShift):

    $ oc process -f openshift-template.yml -p PIPELINE_SCRIPT=Jenkinsfile.with-agents | oc apply -f -
