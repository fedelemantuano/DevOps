# Minikube on windows

https://minikube.sigs.k8s.io/docs/drivers/hyperv/  
    
    # Install Hyper-V
    Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Hyper-V -All
    # config
    minikube config set driver hyperv
    minikube config set hyperv-virtual-switch ExtNet
    # start
    minikube start
    minikube dashboard
    # start debug 
    minikube start --alsologtostderr -v=7
