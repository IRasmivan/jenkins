# ![Jenkins Implementation into Kubernetes - By Rasmi](jenkins.png)

## Jenkins in Kubernetes


### Deploye Jenkines Dependencies

Run the command to deploye deployment

```
kubectl create -f jenkins-deployment.yaml
```

### Deploye Service (NodePort)

Run the next command to deploye Service

```
kubectl create -f jenkins-service.yaml
```

### Error while creating deployment and service

If the below stament caused any error, it might be due to the Kubectl config. Run the below comment to correct them if required.

```
ls -l $(which kubectl)
```

which returns as

```
/usr/local/bin/kubectl -> /Applications/Docker.app/Contents/Resources/bin/kubectlcode.
```

Now we have to overwrite the symlink with kubectl which is installed using brew

```
rm /usr/local/bin/kubectl
brew unlink kubernetes-cli && brew link kubernetes-cli
```

To Verify

```
ls -l $(which kubectl)
```
