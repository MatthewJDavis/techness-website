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

[Ansible for DevOps]: https://www.ansiblefordevops.com/