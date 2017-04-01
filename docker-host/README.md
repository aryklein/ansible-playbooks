## Docker host deployment

- Tested with Ansible 2.2
- Expects Ubuntu 16.04 LTS hosts

This playbook deploys a simple Docker host to run Docker containers
To use, copy the `hosts.example` file to `hosts` and edit the `hosts`
inventory file to include the names or domains of the servers you want
to deploy.

Then run the playbook, like this:

```
$ ansible-playbook -i hosts docker-host.yml
```

