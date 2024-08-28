
Install Go

```
# Need to have root privilege to perform this
sudo su # If not root
curl -OL  https://go.dev/dl/go1.22.3.linux-amd64.tar.gz \
&&  rm -rf /usr/local/go && tar -C /usr/local -xzf go1.22.3.linux-amd64.tar.gz \
&& export PATH=$PATH:/usr/local/go/bin
```

Check go version
```
go version

#If go is not on PATH
export PATH=$PATH:/usr/local/go/bin
go version
```

Download & Install kubebuilder
```
# Need root privilege 
curl -L -o kubebuilder "https://go.kubebuilder.io/dl/latest/$(go env GOOS)/$(go env GOARCH)"
chmod +x kubebuilder && mv kubebuilder /usr/local/bin/

# check kubebuilder version
kubebuilder version

```

Create a folder - my-operator - and this will hold all code for my operator

```
mkdir my-operator
cd my-operator
```

Scaffold a kubebuilder application in this folder - my-operator

```
kubebuilder init --repo example.com

# Create Foo API
kubebuilder create api --group tutorial --version v1 --kind Foo
# Yes to creating Resource & Controller

```

Complete tutorial : https://betterprogramming.pub/build-a-kubernetes-operator-in-10-minutes-11eec1492d30 <br>
