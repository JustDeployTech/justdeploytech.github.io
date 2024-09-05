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

If you're on a Mac, you may see the following error:

```shell
{"msg": "crypt.crypt not supported on Mac OS X/Darwin, install passlib python module. crypt.crypt not supported on Mac OS X/Darwin, install passlib python module"}
```

In this case, just run the following on your terminal and try again:

```shell
pip install passlib
```

Once you repeat the ansible-playbook command, you can check that your server has been configured by going to your browser and typing in your server's IP address. You should see a page that says "Caddy".

![Welcome to caddy page]({{ 'assets/images/01-server-setup-caddy.png' | relative_url }})

Pat yourself on the back, you've just configured your server! 🎉

## What's Next?

The server is configured, it's time we setup your application(s).\
<span class="fs-6 float-right"> 
  [🚀 Time to go live >>]({% link tutorials/step4.md %}){: .btn }
</span>