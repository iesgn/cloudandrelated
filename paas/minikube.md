# minikube: Jugando con kubernetes 

    curl -Lo minikube https://storage.googleapis.com/minikube/releases/v0.30.0/minikube-linux-amd64 && chmod +x minikube && sudo cp minikube /usr/local/bin/ && rm minikube

    curl -Lo minikube https://storage.googleapis.com/minikube/releases/v0.30.0/minikube-linux-amd64 && chmod +x minikube && sudo cp minikube /usr/local/bin/ && rm minikube

    $ minikube start --vm-driver=virtualbox
    Starting local Kubernetes v1.10.0 cluster...
    Starting VM...
    ...
    Kubectl is now configured to use the cluster.
    Loading cached images from config file.

Una vez terminado podemos ejecutar la siguiente instrucción para comprobar los nodos que forman mi cluster:

    $ kubectl get nodes
    NAME       STATUS    ROLES     AGE       VERSION
    minikube   Ready     master    54s       v1.10.0

Y las versiones del cliente y el servidor:

    $ kubectl version
    Client Version: version.Info{Major:"1", Minor:"10", GitVersion:"v1.10.0", GitCommit:"fc32d2f3698e36b93322a3465f63a14e9f0eaead", GitTreeState:"clean", BuildDate:"2018-03-26T16:55:54Z", GoVersion:"go1.9.3", Compiler:"gc", Platform:"linux/amd64"}
    Server Version: version.Info{Major:"1", Minor:"10", GitVersion:"v1.10.0", GitCommit:"fc32d2f3698e36b93322a3465f63a14e9f0eaead", GitTreeState:"clean", BuildDate:"2018-03-26T16:44:10Z", GoVersion:"go1.9.3", Compiler:"gc", Platform:"linux/amd64"}
