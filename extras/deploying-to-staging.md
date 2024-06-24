---
title:  Deploying to Staging
layout: default
nav_order: 3.7
parent: 🛸 Extras
---

## Introduction

Sometimes you don't want your application to be available to the whole world. JustDeploy lets you deploy your application on a staging environment so you can test it before making it available to the public.

## Configuring

Back in step 2, you would have set up your application. If you haven't done that yet, you can follow the steps in the [tutorials section]({% link tutorials/step2.md %}).

To ensure the application is only available to you, you can set up a staging environment. This will allow you to test your application before making it available to the public.

Here are the changes you need top make to your `config.yml` file:

```yaml
application:
  - name: "JustDeploy Homepage"
    domain: "www.justdeploy.tech justdeploy.tech"
    description: "JustDeploy helps you deploy your application to your own server in minutes not weeks"
    repository: "justdeploy/justdeploy.tech"
    type: "preview"
    branch: "branch-name"
    port: 3001
    start_command: "npm run build; npm run start"
    variables:
      - key: "NODE_ENV"
        value: "production"
      - key: "PORT"
        value: "3001"
```

Noticed we've added a `type` and `branch` field. The `type` field is set to `preview` and the `branch` field is set to the name of the branch you'd like to deploy.

Once you've made that change, you can go ahead and run the `02.application_setup.yml` playbook again.

```shell
ansible-playbook -i inventory 02.application_setup.yml
```

{: .note }
Refer to [checking your apps]({% link extras/checking.md %}) to see how you can open up the pot to access your staging environment as it won't be accessible through your domain name, but directly via the IP address that is only available to you.

## Staging & Live at the same time?

I gotchu! You can deploy your application to both staging and live at the same time. Just add another application to your `config.yml` file with the `type` field set to `live` or just remove it as it will default to live.

```yaml
application:
  - name: "JustDeploy Homepage - Staging"
    domain: "www.justdeploy.tech justdeploy.tech"
    description: "JustDeploy helps you deploy your application to your own server in minutes not weeks"
    repository: "justdeploy/justdeploy.tech"
    type: "preview"
    branch: "branch-name"
    port: 3001
    start_command: "npm run build; npm run start"
    variables:
      - key: "NODE_ENV"
        value: "production"
      - key: "PORT"
        value: "3001"
application:
  - name: "JustDeploy Homepage"
    domain: "www.justdeploy.tech justdeploy.tech"
    description: "JustDeploy helps you deploy your application to your own server in minutes not weeks"
    repository: "justdeploy/justdeploy.tech"
    type: "live"
    port: 3002
    start_command: "npm run build; npm run start"
    variables:
      - key: "NODE_ENV"
        value: "production"
      - key: "PORT"
        value: "3002"
```

## Going live

When you're happy with your changes, merge them back to your `main` branch and run the `02.application_setup.yml` playbook again. This time, set the `type` field to `live` in your `config.yml` file.