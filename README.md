# Gitea Runner

* Create the runner token

```sh
kubectl create secret generic gitea-runner-token --namespace gitea --dry-run=client --from-literal=act-runner-token='lolmyrunnertoken' -o yaml | kubeseal --controller-namespace system --controller-name sealed-secrets -o yaml
```

## Increase parallel jobs execution

```yaml
act-runner:
  act_runner:
    parallel_jobs: 5
```

* Doc is [here](https://gitea.com/gitea/act_runner)
