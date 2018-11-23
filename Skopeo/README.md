# Skopeo
HowTo install and config skopeo on RHEL 7

### Install GO

HowTo ref : [https://tecadmin.net/install-go-lang-on-centos/](https://tecadmin.net/install-go-lang-on-centos/)

Binary Distribution page: [https://golang.org/dl/](https://golang.org/dl/)

```bash
wget https://dl.google.com/go/go1.11.2.linux-amd64.tar.gz
tar -xvf go1.11.2.linux-amd64.tar.gz
mv go /usr/local
```

Set up GO Environment and testit:

```bash
export GOROOT=/usr/local/go
mkdir $HOME/GoProjects
export GOPATH=$HOME/GoProjects
export PATH=$GOPATH/bin:$GOROOT/bin:$PATH
go version
go env
```

### Build Skopeo

```bash
git clone https://github.com/containers/skopeo $GOPATH/src/github.com/containers/skopeo
yum update
yum install libgpgme-dev libassuan-dev btrfs-progs libdevmapper-dev libostree-dev
cd $GOPATH/src/github.com/containers/skopeo && make binary-local
mv $GOPATH/src/github.com/containers/skopeo/skopeo /usr/local/bin/
```

### Build Skopeo without network
After downloading the zip from https://github.com/containers/skopeo
```bash
wget --no-check-certificate --no-proxy  https://mynexus.local/my-raw-repo/skopeo-master.zip
mkdir -p $GOPATH/src/github.com/containers
unzip skopeo-master.zip -d $GOPATH/src/github.com/containers/
mv $GOPATH/src/github.com/containers/skopeo-master/ $GOPATH/src/github.com/containers/skopeo/
```

### Reference

* [skopeo Github repo](https://github.com/containers/skopeo)
* [skopeo install](https://github.com/containers/skopeo/blob/master/README.md)
* [skopeo create serviceaccount on openshift](https://github.com/nmasse-itix/OpenShift-Examples/tree/master/Using-Skopeo)
