# java-trunk-pipeline

Create a Jenkins slave image which contains the `skopeo` command, to be able to copy images between registries:

    oc apply -f slave-image-mgmt-centos.yml

Create the pipeline:

    oc apply -f pipeline.yml
