---
layout: default
title: "Step 2: Configurations"
nav_order: 2
parent: 📚 Tutorials
---

## Configuring

### Finish your inventory
{: .fs-5 .text-blue-000 }

While you still have your `{{ site.domain }}/inventory` file open, let's go ahead and add one or two things to it.

Replace `YOUR_SERVER_IP` with the IP address your VPS gave to you. This will look something like `238.162.20.166`.

```yaml
[vps]
YOUR_SERVER_IP

[vps:vars]
ansible_user=
ansible_ssh_private_key_file=~/.ssh/id_rsa
#ansible_port=23
```

(optional) You can uncomment the port parameter if using anything other than the default port 22 for SSH. If you're using port 22, then ignore this.

## Configuration Options

Now that you've finished configuring your inventory, go ahead and open up `{{ site.domain }}/config.yml` and change the values you see fit. The default options are mostly fine

### `install_packages`
{: .d-inline-block }

Recommended
{: .label .label-green }

- **Description**: Specifies whether to install initial packages listed under `software_packages`.
- **Values**: 
  - `true`: Initial packages will be installed.
  - `false`: Initial packages will not be installed.
- **Default**: `true`

### `configure_security`
{: .d-inline-block }

Recommended
{: .label .label-green }

- **Description**: Specifies whether to configure security settings (firewall, SSH).
- **Values**: 
  - `true`: Security settings will be configured.
  - `false`: Security settings will not be configured.
- **Default**: `true`

### `change_port`

- **Description**: Specifies whether to change the SSH port.
- **Values**: 
  - `true`: SSH port will be changed.
  - `false`: SSH port will not be changed.
- **Default**: `false`

### `port_number`

- **Description**: The port number to which the SSH port will be changed if `change_port` is set to `true`.

### Create New User
{: .d-inline-block }

🚨 Recommended
{: .label .label-green }

- **Description**: Specifies whether to create a new user.
- **Values**: 
  - `true`: A new user will be created.
  - `false`: A new user will not be created.
- **Default**: `true`

### `new_user_name`

- **Description**: The username of the new user to be created if `create_new_user` is set to `true`.

### `setup_webserver`
{: .d-inline-block }

Recommended
{: .label .label-green }

- **Description**: Specifies whether to set up a web server on the VPS.
- **Values**: 
  - `true`: A web server will be set up.
  - `false`: A web server will not be set up.
- **Default**: `true`

### `application_port`

- **Description**: The port number on which your application will run. This is the port you've been running your application on developer mode. 

### ``application_start_command``

- **Description**: The command to start the application. This could be something like `npm run build; npm run start` for production.

### `application_variables`

- **Description**: Environment variables required for the application.
- **Format**: List of key-value pairs.

### `github_username`

- **Description**: Your GitHub username.

### `github_token`

- **Description**: Your GitHub access token. You can get some help to generate one by following the simple steps [here](/extras/github-access-token.md)

### `github_repo`

- **Description**: The name of the GitHub repository where your application code lives.

## What's Next?

We're so close. Head to Step 3 to run JustDeploy on your server.\
<span class="fs-6 float-right"> 
  [🚀 Step 3 >>](/tutorials/step3){: .btn }
</span>
