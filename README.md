- š Hi, Iām @RadFromOrange
- š Iām interested in ...
- š± Iām currently learning ...
- šļø Iām looking to collaborate on ...
- š« How to reach me ...

<!---
RadFromOrange/RadFromOrange is a āØ special āØ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->


apiVersion: skaffold/v2beta29
kind: Config
metadata:
  name: jupyterhub-on-kubernetes-master
build:
  artifacts:
  - image: beta
    context: images/jupyter-hub
    docker:
      dockerfile: Dockerfile
deploy:
  kubectl:
    manifests:
    - jupyter-hub/jupyter-hub/deployment.yaml
    - jupyter-hub/jupyter-hub/pvc.yaml
    - jupyter-hub/jupyter-hub/rbac.yaml
    - jupyter-hub/jupyter-hub/service.yaml
    - jupyter-hub/proxy/deployment.yaml
    - jupyter-hub/proxy/service.yaml

