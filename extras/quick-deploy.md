---
title:  Quick Deploy
layout: default
nav_order: 3.6
parent: 🛸 Extras
---

## Introduction

Sometimes you just need to do a little update to your application and don't want to go through the entire deployment process. This is where the quick deploy feature comes in handy.

If your application has already been configured, this task will help you deploy just that without stopping any of the other apps you my have already running.

## Prerequisites

Your code needs to have been previously deployed and configured. If you haven't done that yet, you can follow the steps in the [tutorials section]({% link tutorials/step4.md %}).

Once your code has been committed and pushed to your repository, you can use the quick deploy feature to update your application.

## Running the Command

To quickly deploy your application, run the following command:

```shell
ansible-playbook -i inventory 99.extras_setup.yml --tags quick_deploy -e "repository=NAME_OF_YOUR_REPOSITORY"
```

Make sure to replace `NAME_OF_YOUR_REPOSITORY` with the name of the repository you configured in your `config.yml` file.

## Conclusion

The quick deploy feature is a convenient way to update your application without affecting other running services. By specifying the repository name, you can quickly deploy changes to your application without the need to restart the entire server or other applications. This can be particularly useful for minor updates or bug fixes that don't require a full deployment cycle.
