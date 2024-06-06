---
title: 🚀 Get Started
layout: home
nav_order: 1
---

## Hey builder, it's time to deploy! 👋

Here's a quick overview of this deploying tool. Follow along to get your environment up and running.

Once you're done, start with [this tutorial]({% link tutorials/step1.md %}) to setup your server in 5 minutes. Let's deploy that product, FAST ⚡️

### Install Ansible Locally

Ansible is an open-source automation platform used to streamline IT tasks, manage infrastructure, and automate workflows across various systems and environments.

#### Mac OS
{: .fs-5 .text-blue-000 }

To install Ansible on a Mac, you can use Homebrew. First, ensure you have Homebrew installed. If not, you can install it by running the following command in your terminal:

```shell
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Once Homebrew is installed, you can install Ansible by running:

```shell
brew install ansible
```

#### Linux
{: .fs-5 .text-blue-000 }

On Linux systems, you can typically install Ansible using the package manager specific to your distribution.

For example, on Ubuntu or Debian-based systems, you can use apt:

```shell
sudo apt update
sudo apt install ansible
```

On CentOS or Red Hat Enterprise Linux (RHEL), you can use yum:

```shell
sudo yum install ansible
```

#### Windows
{: .fs-5 .text-blue-000 }

On Windows, Ansible can be installed via the [Windows Subsystem for Linux (WSL)](https://docs.microsoft.com/en-us/windows/wsl/install-win10) or by using a third-party tool like Cygwin.

For WSL installation, you can follow the official Microsoft documentation on how to set up WSL. After having installed WSL, you can [install Ansible through apt](https://docs.ansible.com/ansible/latest/user_guide/windows_faq.html#can-ansible-run-on-windows) similar to Linux users.

Once Ansible is installed, you can verify the installation by running:

```shell
ansible --version
```

This command should display the installed Ansible version.

{: .highlight }
> Watch out for the version
>
> Make sure you're using version 2.1 or higher. Older versions haven't been tested and might not work.

<span class="fs-6 float-right"> 
  [Setup your server in 5 minutes]({% link tutorials/step1.md %}){: .btn }
</span>