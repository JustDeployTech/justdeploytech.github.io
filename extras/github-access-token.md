---
title:  Setup a Github Access Token
layout: default
nav_order: 3.1
parent: 🛸 Extras
---
## Setting up a Github Access Token

To set up a GitHub access token for authentication, follow these steps:

1. **Generate a Personal Access Token:**
   - Go to your GitHub account settings by clicking on your profile picture in the top-right corner and selecting "Settings".
   - In the left sidebar, click on "Developer settings", then click on "Personal access tokens".
   - Click on the "Generate new token" button and choose "For General Use"
   - Provide a token description to identify its usage.
   - Choose `repo` and `admin:repo_hook` as the scope.
   - Click on the "Generate token" button at the bottom of the page.
   - GitHub will generate a new personal access token. Copy this token immediately as it won't be displayed again.

2. **Store the Token Securely:**
   - Once you've generated the token, make sure to store it securely. Treat it like a password and never share it with others or include it in publicly accessible code repositories.
   - You can store the token in a secure location such as a password manager or environment variables on your local machine.

3. **Use the Token in Your Application:**
   - When using the token in your application or scripts, pass it as an authentication header or as a parameter in your API requests.
   - Ensure that your application securely handles the token and doesn't expose it unintentionally.

If you just came here to set this up and are ready to finish off your configs, [click here](/tutorials/step2#github_token) and I'll take you back there.
