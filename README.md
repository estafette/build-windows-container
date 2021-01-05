
To start building a Windows (multistage) Dockerfile and push it into a repository execute the following

```bash
export GIT_REPOSITORY=...
export DOCKERFILE=...
export DOCKER_IMAGE=...
export DOCKER_USERNAME=...
export DOCKER_PASSWORD=...

cat build-container-job.yaml | envsubst \$GIT_REPOSITORY,\$DOCKERFILE,\$DOCKER_IMAGE,\$DOCKER_USERNAME,\$DOCKER_PASSWORD | kubectl apply -f -
```

Tail the

kubectl logs -f -l app=build-windows-dockerfile -n build-windows-dockerfile

Once done remove the job with

```bash
kubectl delete job build-windows-dockerfile -n build-windows-dockerfile
```
