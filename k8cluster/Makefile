
help: 		## This help
	@fgrep -h "##" $(MAKEFILE_LIST) | fgrep -v fgrep | sed -e 's/\\$$//' | sed -e 's/##//'

roles:		## Clone repo containing ansible roles to make Kubernetes cluster
	git clone https://github.com/mbovo/k8i.git k8i

up:		## Startup vagrant nodes
	vagrant up

cluster:	## Apply to nodes the ansible roles (see inventory.yml)
	ANSIBLE_ROLES_PATH="./k8i/roles" ansible-playbook -i inventory.yml -u root -b --ssh-extra-args "-o UserKnownHostsFile=/dev/null -o StrictHostKeyChecking=no" k8i/playbooks/setup.yaml 

destroy: 	## Destroy vagrant nodes
	vagrant destroy -f

clean:		## Clean up roles directory
	rm -rf k8i

all:		## Everything
	destroy clean roles up cluster