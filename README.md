# syn-deploy-ops

Gitops experiment with Digital Ocean Kubernetes Service, Flux CD and github

## insecure-reveal-env-variables

https://github.com/aljorhythm/insecure-reveal-env-variables

Updates to the repo will publish an image to Docker Hub and picked up by FluxCD in the K8s cluster
## Sample commands

Trigger reconciliation
`flux reconcile source git flux-system`

Get all iamges
`flux get images all --all-namespaces`

## References

https://github.com/digitalocean/Kubernetes-Starter-Kit-Developers/blob/main/08-kubernetes-sealed-secrets/README.md
https://github.com/digitalocean/Kubernetes-Starter-Kit-Developers/blob/main/15-continuous-delivery-using-gitops/fluxcd.md

https://fluxcd.io/docs/guides/image-update/
https://fluxcd.io/docs/use-cases/gh-actions-manifest-generation/