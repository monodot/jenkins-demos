# dynamic-branch

A lite demo for how to specify a branch name dynamically when running a Jenkins job.

Setup instructions for a _Freestyle job_:

1. Create a freestyle job in Jenkins:
1. (If running in OpenShift:) Restrict where this project can be run -> Label Expression = `maven` (this is so that Jenkins has a Maven `mvn` binary which it can use)
1. Tick _This project is parameterised_ -> String Parameter:
    - Set Name = `branchName`
    - Set Default Value = `master`
1. Select _Git_ for Source Code Management:
    - Set repository URL = `https://github.com/monodot/jenkins-demos`
    - Branches to Build - Branch Specifier (blank for 'any') = `*/${branchName}`
1. Set Build step -> invoke top-level Maven targets:
    - Set Goals = `-B verify`
    - Set POM = `dynamic-branch/pom.xml`

Now run the job, setting the `branchName` parameter to one of:

- `master` will use the master branch where the Maven POM has been configured with version `1.0`
- `dynamic-branch` will use the given branch where the Maven POM has been configured with version `1.0-DYNAMIC-BRANCH`

