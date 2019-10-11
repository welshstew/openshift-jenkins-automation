# openshift jenkins automation

playbooks to help me bootstrap a dev environment with jenkins for fun.


- login to cluster
- Create projects 
- Create https://github.com/welshstew/e2e-pipeline-sample as a sample


```
sudo dnf install python2-virtualenv
sudo dnf install /usr/bin/virtualenv
virtualenv --python /usr/bin/python2.7 env27
. env27/bin/activate

```


```
python3 -m venv env --system-site-packages
. env/bin/activate

```

```
ansible-galaxy install -r requirements.yml


ansible-playbook create-cicd-project.yml --extra-vars "@extra-vars.yml"
ansible-playbook teardown.yml --extra-vars "@extra-vars.yml"
ansible-playbook test-role.yml --extra-vars "@extra-vars.yml" -e'ansible_python_interpreter=/usr/bin/python3'



INFO Then you can access it by running 'oc login -u developer -p developer https://api.crc.testing:6443' 
INFO To login as an admin, username is 'kubeadmin' and password is F44En-Xau6V-jQuyb-yuMXB 


```

Thanks: https://cinhtau.net/2019/02/14/ansible-openshift-python/