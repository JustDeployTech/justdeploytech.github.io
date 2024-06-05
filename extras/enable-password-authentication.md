---
title:  Enable Password Authentication
layout: default
nav_order: 3.3
parent: 🛸 Extras
---

## Enable Password Authentication for SSH

### 1. Open the SSH Configuration File

First, you need to open the SSH configuration file, which is typically located at `/etc/ssh/sshd_config`.

1. Open the virtual terminal for your new server.
2. Use a text editor to open the `sshd_config` file. For example, you can use `nano`:

   ```bash
   sudo nano /etc/ssh/sshd_config
   ```

### 2. Modify the SSH Configuration File

Locate the following lines in the file. If they are not present, you can add them.

1. Look for the line that says `PasswordAuthentication`. If it is commented out (has a `#` at the beginning), uncomment it by removing the `#` and ensure it says `yes`:\

   ```bash
   PasswordAuthentication yes
   ```

### 3. Save the Changes and Exit

After making the changes:

1. If you are using `nano`, save the file by pressing `Ctrl + O`, then press `Enter` to confirm.
2. Exit the editor by pressing `Ctrl + X`.

### 4. Restart the SSH Service

To apply the changes, restart the SSH service using the following command:

```bash
sudo systemctl restart sshd
```

## Troubleshooting

- If you are still unable to use password authentication, ensure that there are no conflicting settings in the `sshd_config` file.
- Make sure the SSH service restarted without errors by checking its status:

  ```sh
  sudo systemctl status sshd
  ```

- Verify that your user account is allowed to log in via SSH and that there are no restrictions in place (e.g., `AllowUsers` or `DenyUsers` directives in `sshd_config`).

---

## What's Next?

Click here to head back to configuring JustDeploy\
<span class="fs-6 float-right"> 
  [💥 Step 1{% link tutorials/step1.md %}){: .btn }
</span>
