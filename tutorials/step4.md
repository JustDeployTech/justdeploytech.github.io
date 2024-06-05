---
layout: default
title: "Step 4: Setup your Apps"
nav_order: 4
parent: 📚 Tutorials
---

Now that your server is configured, we're ready to setup your application(s). Back in [step 2](/tutorials/step2.html#application-configuration) we configured the `config.yml` file, which contains the settings for your applications. Which means we're nearly good to go.

## Memory

Apps need memory to run, and the amount of memory they need can vary. If you're running a small app, you might be able to get away with a small server. If you're running a large app, you might need a larger server.

Regardless of how big your apps are, running `npm install` for the first time is likely to need A LOT of memory. If you're on a server with less than 1GB of memory, you might run into problems.

We've got you covered though 💪, we've setup a swap file for you. This is a file on your server that acts like extra memory. It's slower than real memory, but it's better than nothing, and for running `npm install` it's usually enough.

If you're on a server with less than 1GB of memory, head to to the [swap section]({% link extras/swap.md %}) to learn more about how to set up a swap file.

## Running your server task

In the previous section we've executed a playbook that configured our entire server for us, now it's time to run the playbook that will setup our applications.

### Options:

- `-i inventory`: Specifies the inventory file containing the list of hosts on which the playbook tasks will be executed.

- `--ask-pass`: Prompts for the SSH password of the target host. This option is necessary when SSH key-based authentication is not used or available, allowing the user to manually enter the SSH password for connection.

### All together now:

Open up your terminal and from within the `{{site.project}}` directory execute:

```shell
ansible-playbook -i inventory 02.application_setup.yml --ask-pass
```

This command runs the `02.application_setup.yml` playbook, which contains the tasks to setup your applications. The `--ask-pass` option is used to prompt for the SSH password of the target host.

![Building and running applications](https://res.cloudinary.com/drajbvhzx/image/upload/v1717580399/Features/02.application_setup_jdjsxg.gif)

## What's Next?

Your apps are up and running 🚀! You can check them out and see that everything is working as expected.

<span class="fs-6 float-right"> 
  [Checking your apps]({% link extras/checking.md %}){: .btn }
</span>