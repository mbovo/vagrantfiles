
roles:
	git clone https://github.com/mbovo/k8i.git k8i

up:
	vagrant up
	export ANSIBLE_ROLES_PATH="$(pwd)/k8i/roles"
	ansible-playbook -i inventory.yml -u root -b k8 k8i/playbooks/setup.yaml


destroy: 
	vagrant destroy -f

clea:
	rm -rf k8i
