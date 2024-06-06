---
title:  Setup Swap
layout: default
nav_order: 3.3
parent: 🛸 Extras
---

## Setting Up a Swap File with Ansible

## Introduction

A swap file acts as an overflow area for your server's RAM. It allows your system to utilize disk space to free up memory by temporarily moving less active processes out of RAM. This can be particularly useful in systems with limited memory, like a server with only 512MB of RAM.

## Why Use Swap?

- **Prevent Crashes**: When your server runs out of RAM, without swap, it has no choice but to start killing processes, which can lead to crashes and data loss.
- **Improve Performance**: Swap can help improve system responsiveness by allowing the system to shuffle less critical processes onto the disk.
- **Flexibility**: Swap files are easier to resize or remove compared to swap partitions.

## A common error message

The following error message can occur when you run out of memory while installing dependencies for your projects

```shell
"msg": "", "rc": -9, "stderr": "", "stderr_lines": [], "stdout": "", "stdout_lines": []
```

## Run the Playbook

Execute the following command from your terminal:

```shell
ansible-playbook -i inventory 99.extras_setup.yml --tags setup_swap
```

This command runs the `99.extras_setup.yml` playbook with the specific tag `setup_swap`, which targets the tasks associated with setting up the swap file.

![Setup Swap]({{ 'assets/images/setup-swap.png' | relative_url }})

## Verify Swap File Creation

You can rerun the playbook above and see that the task "Create swap file if none exists" and all subsequent tasks are skipped.

## Conclusion

Using swap is a practical way to extend the available memory on your server, especially when upgrading physical RAM isn't an immediate option. With Ansible, automating the setup of a swap file is straightforward and ensures consistency across your infrastructure.

If you just came here to set this up and are ready to run your applications, [click here]({% link tutorials/step4.md %}#memory) and I’ll take you back there.
