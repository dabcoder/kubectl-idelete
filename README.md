## kubectl idelete

Safely delete some Kubernetes resources with a prompt to confirm.
For instance, do you remember deleting a deployment or a statefulset in a production environment? This should help avoiding that!

Note: currently supports `deployments` and `statefulsets` only.

### Install

```
curl -fsS -o /usr/local/bin/kubectl-idelete \
    https://raw.githubusercontent.com/dabcoder/kubectl-idelete/master/kubectl-idelete && \
        chmod +x /usr/local/bin/kubectl-idelete
```

Check that `/usr/local/bin` is in your `$PATH` beforehand.

### How to use it

```
kubectl idelete

Usage: kubectl idelete sts | statefulset | deploy | deploymnent <name> [-n | --namespace] <namespace>
```

For example:

```
kubectl idelete sts consul -n consul

This sts has 3 Running pods, do you want to proceed and delete it (y/n)? This could disrupt the underlying application!"
```
