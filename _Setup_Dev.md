 # GitHub Codespace that has support for Node.JS, pnpm, and Docker.


1. Open your repository in GitHub Codespaces. If needed, clone the repository:


> git clone https://github.com/formbricks/formbricks && cd formbricks

2. Setup NodeJS with nvm (if not already configured):

> nvm install && nvm use

3. Install the dependencies:

> pnpm install

4. Create a .env file from the template:

> cp .env.example .env

5. Generate & set the required secrets:

> sed -i '/^ENCRYPTION_KEY=/c\ENCRYPTION_KEY='$(openssl rand -hex 32) .env
> sed -i '/^NEXTAUTH_SECRET=/c\NEXTAUTH_SECRET='$(openssl rand -hex 32) .env
> sed -i '/^CRON_SECRET=/c\CRON_SECRET='$(openssl rand -hex 32) .env

6. Launch the development setup:

> pnpm go

Use the Codespaces port forwarding to access Formbricks at http://localhost:3000.
