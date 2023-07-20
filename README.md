# AAP GitHub argocd

Workflow:

Job_Template -> Survey -> Create GitHub repo -> push OCP Namespaces CRs -> Create ArgoCD app to syncronize CRs to OCP

## Prerequsites

- community.general collection
  - Python requirements:
    - PyGithub>=1.54

## Build the execution environment

```
ansible-builder build -t quay.io/valeube/ansible-community-ee:latest
```

## Push the image

```
podman push quay.io/valeube/ansible-community-ee:latest
```

## Run the playbook

```
ansible-navigator run -i inventory --eei quay.io/valeube/ansible-community-ee  playbooks/main.yml -vvv -m stdout
```