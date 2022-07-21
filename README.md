## Instructions to make it work:
- Include in the project's root directory a file named `inventory` with the content:
```
[all]
airfryer ansible_host=SERVER-LOCAL-IP ansible_ssh_private_key_file=PATH-TO-PRIVATE-SSH-KEY ansible_port=SSH-PORT
```
- Include in the project's root directory a file named `secret` with the secret key for ansible vault

## Decrypting private.yml
```
ansible-vault encrypt ./group_vars/all/private.yml --vault-password-file ./secret
```

## Running the playbook
```
ansible-playbook main.yml --vault-password-file ./secret
```