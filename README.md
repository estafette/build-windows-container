
To start building a Windows (multistage) Dockerfile and push it into a repository execute the following

```bash
export GIT_REPOSITORY=...
export BUILD_VERSION=...
export DOCKERFILE=...
export DOCKER_IMAGE=...
export DOCKER_USERNAME=...
export DOCKER_PASSWORD=...

cat build-container-job.yaml | envsubst | kubectl apply -f -
```

Once done remove the job with

```bash
kubectl delete job build-windows-dockerfile -n build-windows-dockerfile
```
