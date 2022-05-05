# syn-deploy-ops

Gitops experiment with Digital Ocean Kubernetes Service, Flux CD and github

public IP: [146.190.6.63](http://146.190.6.63)

## insecure-reveal-env-variables

https://github.com/aljorhythm/insecure-reveal-env-variables

Updates to the repo will publish an image to Docker Hub and picked up by FluxCD in the K8s cluster
## Sample commands

Set up
```
export GITHUB_TOKEN=<FILL>
export DO_SPACES_ACCESS_KEY=<FILL>
export DO_SPACES_SECRET_KEY=<FILL>
```

Bootstrap
```
flux bootstrap github --owner=aljorhythm \
--components-extra=image-reflector-controller,image-automation-controller \
--repository=syn-deploy-ops --path clusters/dev \
--personal \
--read-write-key
```

Trigger reconciliation
`flux reconcile source git flux-system`

Get all iamges
`flux get images all --all-namespaces`

Resume image update
`flux resume image update flux-system`

## References

https://github.com/digitalocean/Kubernetes-Starter-Kit-Developers/blob/main/08-kubernetes-sealed-secrets/README.md
https://github.com/digitalocean/Kubernetes-Starter-Kit-Developers/blob/main/15-continuous-delivery-using-gitops/fluxcd.md

https://fluxcd.io/docs/guides/image-update/
https://fluxcd.io/docs/use-cases/gh-actions-manifest-generation/
https://fluxcd.io/docs/guides/image-update/