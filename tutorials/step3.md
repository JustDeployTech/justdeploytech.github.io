---
layout: default
title: "Step 3: Run Server!"
nav_order: 3
parent: 📚 Tutorials
---

Howdy partner 🤠! It's time to run our server tasks. We've split these up in two steps to make sure you follow everything that is happening.

{: .note }
Runs are idempotent (/ʌɪdɛmˈpəʊtnt/), which is a fancy way of saying "if you run this script 10 times you will always end up with the same set of results and no duplication".

Idempotency is important because it's totally normal to change your mind and want to do things a little different.

If you completely change your mind and want to revert every change this script makes, just go ahead and read about our [teardown task]({% link extras/teardown.md %}).

## Updating the inventory

If you created a new user in the previous step, you'll need to update the inventory file with the new user's username. For security reasons we always like to disable root login in that case, so open up `inventory` for one last time and change the `ansible_user` value to the new user's username. I.e.:

```sh
[vps:vars]
ansible_user=teddy
```

## Running your first task

The `ansible-playbook` command is used to execute Ansible playbooks, which are YAML files containing a series of tasks and configurations to be applied to target hosts.

### Options:

- `-i inventory`: Specifies the inventory file containing the list of hosts on which the playbook tasks will be executed.
  
- `01.server_setup.yml`: The filename of the playbook to be executed. In this example, `01.server_setup.yml` is the name of the YAML file containing the server setup tasks.

- `-k`: Prompts for the SSH password of the target hosts. This option is used when SSH key-based authentication is not set up or preferred.

- `-K`: Prompts for the privilege escalation (sudo) password. This option is used when the tasks in the playbook require elevated privileges on the target hosts.

### All together now:

Open up your terminal and from within the `{{site.project}}` directory execute:

```shell
ansible-playbook -i inventory 01.server_setup.yml
```

## What's Next?

The server is configured, it's time we setup your application(s).\
<span class="fs-6 float-right"> 
  [🚀 Step 4 >>]({% link tutorials/step4.md %}){: .btn }
</span>