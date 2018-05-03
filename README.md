# Openshift Tasks APB (Ansible Playbook Bundle)

This repository aims to create an ansible playbook bundle that wraps the openshift-tasks demonstration available in the following repository : [OpenShift Tasks](https://github.com/clerixmaxime/openshift-tasks).

## Prerequisites
* OpenShift 3.7+ with ansible service broker
* apb CLI ([Installaing apb tools](https://docs.openshift.com/container-platform/3.9/apb_devel/cli_tooling.html#apb-devel-cli-install))

It is advised to work directly on a subscribed Red Hat Enterprise Linux to avoid issues regarding access to Red Hat Registry.

## How to use this APB
For more information on how to use and develop APB, please refer to the [official documentation](https://docs.openshift.com/container-platform/3.9/apb_devel/index.html)
### Building the APB
```
git clone https://github.com/clerixmaxime/openshift-tasks-apb.git

cd openshift-tasks-apb

apb build
```

### Push the APB on OpenShift
```
apb push
```
You can verify that your APB has been pushed by typing `apb list`. If your APB does not appear, you can use the command `apb bootstrap` and then `apb relist` to force the service catalog to reload APBs from the OpenShift Ansible Broker.

### Run the APB from the CLI
```
apb run --project ocp-tasks-apb
```
This will run your APB in a project called ocp-tasks-apb.