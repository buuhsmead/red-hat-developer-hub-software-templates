# Tekton CI Method

## Requirements

The Tekton CI Method will require some steps before you are able to run

- Add Quay.io credentials as a secret
- Setup a GitHub webhook for push events
- Add gitHubApp credentials (PAT) as a secret
- Add the secret to the ServiceAccount (SA) named pipeline

```
kind: Secret
apiVersion: v1
metadata:
  name: github-secret
  namespace: app-team-b
  annotations:
    tekton.dev/git-0: 'https://github.com'
data:
  password: U0VDUkVUX1BBVAo=
  username: VVNFUk5BTUVfUEFUCg==
type: kubernetes.io/basic-auth
```

pipeline.yaml needs to be more generic
