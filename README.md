# Bate papo sobre Ansible

Exemplos graduais com ansible feitos em nosso bate-papo.

# Python3 environment and ansible installation
``
python3 -mvenv env
source env/bin/activate
pip install ansible
``

sair do Environment:
``
deactivate
``

# Ansible

## instala sl em host ataulfo
``
ansible -i inventory -m apt -a "update_cache=yes name=sl state=present"
``

## coleta informações do host ataulfo
``
ansible -i inventory -m setup ataulfo
``

## coleta informações filtrando especificamente do host teofranazia
``
ansible -i inventory -m setup -a "filter=ansible_distribution*" teofranazia
``

## executa pagina.yaml passando variável
``
ansible-playbook -i inventory pagina.yaml -e '{ amostra: true }'
``

## cria role exemplo
``
ansible-galaxy init exemplo
``

## executa playbook site.yaml
``
ansible-playbook -i ../inventory site.yaml
``

