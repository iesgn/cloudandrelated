# Minishift: Playing around with OpenShift v3

[minishift](https://docs.okd.io/latest/minishift/index.html) is an
application that can be used to deploy "easily" a openshift cluster on
one
node. [Virtualbox](https://docs.okd.io/latest/minishift/getting-started/setting-up-virtualization-environment.html),
but
[kvm](https://docs.okd.io/latest/minishift/getting-started/setting-up-virtualization-environment.html#setting-up-kvm-driver)
or other hypervisors can also be used. See the docs for further information.

## Minishift installation

Virtualbox 5.1.12 or higher is needed.

From the [download
site](https://github.com/minishift/minishift/releases), the latest
release can be downloaded and its contents extracted.

    $ minishift version                       
    minishift v1.27.0+707887e

## Creating the openshift "cluster"

Initializing the cluster (it takes several minutes):

    $ minishift start
    minishift start       
    -- Starting profile 'minishift'
    ...
    OpenShift server started.

    The server is accessible via web console at:
        https://192.168.99.100:8443/console

    You are logged in as:
        User:     developer
        Password: <any value>

    To login as administrator:
        oc login -u system:admin

A new virtualbox virtual machine is created and all the applications
needed installed on it. 


