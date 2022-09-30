- 👋 Hi, I’m @RadFromOrange
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
RadFromOrange/RadFromOrange is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
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

