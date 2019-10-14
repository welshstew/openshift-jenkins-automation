# openshift jenkins automation

Playbooks to help me bootstrap a dev environment with jenkins for fun.  What does it do:


- login to cluster
- Create projects 
- Create a persistent jenkins
- Create https://github.com/welshstew/e2e-pipeline-sample as a sample
- Triggers the pipeline to build and deploy the project in the dev namespace
- Deploys the application in the release namespace

What you need to do:

Define a file like `extra-vars.yml` as per below:

```
ocp_server: https://api.crc.testing:6443
ocp_username: developer
ocp_password: developer
github_username: AAAAA
github_password: AAAAA
```


## Some Python stuff for a virtualenv

```
sudo dnf install python2-virtualenv
sudo dnf install /usr/bin/virtualenv
virtualenv --python /usr/bin/python2.7 env27
. env27/bin/activate

```

OR

```
python3 -m venv env --system-site-packages
. env/bin/activate

```

### How to run:

```
ansible-galaxy install -r requirements.yml
ansible-playbook create-cicd-project.yml --extra-vars "@extra-vars.yml"
ansible-playbook teardown.yml --extra-vars "@extra-vars.yml"
ansible-playbook test-role.yml --extra-vars "@extra-vars.yml" 

```

Thanks: https://cinhtau.net/2019/02/14/ansible-openshift-python/
