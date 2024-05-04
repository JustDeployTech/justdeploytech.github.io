---
layout: default
title: "Step 1: SSH Keys or Nah?"
nav_order: 1
parent: 📚 Tutorials
---
## To SSH or Not?

SSH keys offer superior security over passwords due to their strong encryption, elimination of password sharing, immunity to password guessing attacks, and ease of revocation and central management. Their random, lengthy nature makes them highly resistant to brute-force attacks and enhances overall security, particularly in environments with multiple users or systems.

## But here's the tradeoff

The tradeoff with SSH keys lies in the complexity of key management, including generation, distribution, and revocation, which can become a single point of failure if not properly secured. While offering enhanced security, SSH keys lack the flexibility of password-based authentication, particularly in scenarios requiring access from untrusted devices or locations, necessitating careful consideration of security versus usability and operational concerns.

## Options

### YOLO

Just add your SSH username to `ansible_user` in `{{ site.domain }}/inventory` and you're good to go.

### But security...
{: .d-inline-block }

Recommended
{: .label .label-green }

I hear you, in that case there's a few extra steps we will need.

1. Generate SSH Key Pair:

   - On your local machine, open a terminal.
   - Use the `ssh-keygen` command to generate a new SSH key pair. You can accept the default location and optionally provide a passphrase for added security.

    ```bash
    ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
    ```

   - This command will generate a new SSH key pair (public and private) and save it to the default location (`~/.ssh/id_rsa` for the private key and `~/.ssh/id_rsa.pub` for the public key).

2. Copy Public Key to Remote Server:

   - Use the `ssh-copy-id` command to copy your public SSH key to the remote server. Replace username and hostname with your remote server's username and hostname/IP address.

    ```bash
    ssh-copy-id username@hostname
    ```

   - User `-p port_number` to connect to the specified SSH port on the server, instead of the default port 22.
   - This command will prompt you for your remote server password. Enter it to complete the process. Your public key will be added to the `~/.ssh/authorized_keys` file on the remote server, allowing you to authenticate using your private key.

3. Test SSH Connection:

    - Try connecting to your remote server using SSH. If everything is set up correctly, you should be able to log in without entering a password.

    ```bash
    ssh username@hostname
    ```

4. Update Ansible Inventory:

    - Once SSH key-based authentication is working, you can update your Ansible `inventory` file (vps:vars) to use the SSH key for authentication instead of a password. Make sure you uncomment `ansible_ssh_private_key_file`

    ```bash
    ansible_user=username 
    ansible_ssh_private_key_file=~/.ssh/id_rsa
    ```
