# Setting up git on kali linux 04-04-2024

1. ### HTTPS with Username and Password:

If you're using HTTPS for authentication, you can configure Git to cache your credentials so that you don't have to enter them every time. Here's how:

>`git config --global credential.helper cache`

This command tells Git to use a credential cache to store your credentials temporarily. By default, Git will cache your credentials for 15 minutes.

If you want to change the caching timeout, you can specify it using the --timeout option, for example:

>`git config --global credential.helper 'cache --timeout=3600'`

This command sets the caching timeout to 1 hour (3600 seconds).

2. ### SSH Keys:

If you're using SSH for authentication, you need to ensure that your SSH keys are properly configured. Typically, this involves generating SSH keys and adding your public key to your Git hosting service (e.g., GitHub, GitLab). Here's a general outline of the process:

a. Generate an SSH key pair (if you haven't already):

>`ssh-keygen -t rsa -b 4096 -C "your_email@example.com"`

b. Add your SSH key to the SSH agent:

>`ssh-add ~/.ssh/id_rsa`

c. Copy your SSH public key (~/.ssh/id_rsa.pub) and add it to your Git hosting service's SSH settings.

3. ### HTTPS with Personal Access Tokens (PAT) or OAuth Tokens:

Some Git hosting services, like GitHub, allow you to use Personal Access Tokens or OAuth Tokens for authentication over HTTPS. To set this up:

a. Generate a Personal Access Token or OAuth Token on your Git hosting service's website.

b. Use the following command to configure Git to use the token:

>`git config --global credential.helper store`

Then, when you push or pull from the repository, Git will prompt you for your username and token. After entering them once, Git will remember them.

---