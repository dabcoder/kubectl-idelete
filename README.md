## kubectl idelete

### Disclaimer

This is a kubectl plugin that has not been tested in production nor even in a staging environment, currently in development using minikube for testing. Mostly an exercise in writing a kubectl plugin for the first time. Use it at your own risks.

Aim: Safely delete some Kubernetes resources with a prompt to confirm.

Note: currently supports `deployments` and `statefulsets` only.

### Install

```
curl -sS -o /usr/local/bin/kubectl-idelete \
    https://raw.githubusercontent.com/dabcoder/kubectl-idelete/master/kubectl-idelete && \
        chmod +x /usr/local/bin/kubectl-idelete
```

Check that `/usr/local/bin` is in your `$PATH` beforehand.

### How to use it

```
kubectl idelete

Usage: kubectl idelete sts | statefulset | deploy | deploymnent <name> [-n|--namespace] <namespace>
```

The order of arguments matter. i.e. the namespace `-n <namespace>` needs to be passed at the end.
For example:

```
kubectl idelete sts consul -n consul

This sts (consul) has 3 Running pods, do you want to proceed and delete it  (only "yes" will be accepted)? This could disrupt the underlying application!"
```
