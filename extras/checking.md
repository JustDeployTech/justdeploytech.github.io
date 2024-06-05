---
title:  Checking our apps
layout: default
nav_order: 3.5
parent: 🛸 Extras
---

If you try to hit your application you will see that it's not working. This is because we haven't opened up the firewall port for our application yet.

So trying something like `http://YOUR_IP_ADDRESS:PORT` will not work. I usually like to check this first before configuring DNS, so let's go ahead and open up the port.

## Why Open Ports?

When deploying an application, especially web applications, it is essential to open specific network ports to allow external access to the application. These ports enable users to connect to the services running on your server. For example, web applications typically need ports like 80 (HTTP) or 443 (HTTPS) to be open for users to access the site. Similarly, custom applications may require other ports, such as 3000 for a Node.js application, to be accessible.

## Security Considerations

Opening ports can expose your application to the internet, which poses security risks. To mitigate these risks, it's crucial to restrict access to only trusted sources. By configuring the firewall to allow access only from your IP address, you limit potential threats and unauthorized access while still being able to manage and test your application remotely.

### Opening Ports Securely

The playbook `99.extras_setup.yml` contains several utility tasks, including opening ports securely.

### Running the Command

To open the ports you configured for your application in `_config.yml`, run the following Ansible command:

```bash
ansible-playbook -i inventory 99.extras_setup.yml --tags open_ports
```

### What This Command Does

- **`ansible-playbook -i inventory 99.extras_setup.yml --tags open_ports`**:
  - **`-i inventory`**: Specifies the inventory file containing the list of target hosts.
  - **`99.extras_setup.yml`**: The playbook file that includes the tasks to open the application ports.
  - **`--tags open_ports`**: Ensures only the tasks tagged with `open_ports` are executed, which are responsible for configuring the firewall.

After doing this, go ahead and try to hit your application again. You should see it working now. If not, you might want to ssh into your server and check the pm2 logs by executing `pm2 logs` to see what's going on.
