# techness-website

Ansible playbooks to configure website with nginx.

Uses nginx and let's encrypt for cert.

From [Ansible for DevOps] by Jeff Geerling chapter 13.

```bash
ansible-galaxy install -r requirements.yml 
```

## inventory file

Create the inventory file like below.
The domain name DNS entry A record should be updated to point to the server's IP address and should be resolvable.

```ini
[letsencrypt]
*domainname*

[letsencrypt:vars]
ansible_user=username
letsencrypt_email=email
```

To run playbook.

```bash
ansible-playbook -i inventory  main.yml
```

## Azure resources

azure-playbook.yml contains the tasks to create the resources for the server in Azure.

To set the [credentials]:

```bash
export AZURE_CLIENT_ID=
export AZURE_SECRET=
export AZURE_SUBSCRIPTION_ID=
export AZURE_TENANT=
```

[Ansible for DevOps]: https://www.ansiblefordevops.com/
[credentials]: https://docs.ansible.com/ansible/latest/scenario_guides/guide_azure.html