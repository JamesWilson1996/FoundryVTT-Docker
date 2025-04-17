# FoundryVTT-Docker
A setup for using Felddy's docker image for FoundryVTT with traefik. All settings configured using the .env file.
Steps are written assuming no prior knowledge of using CLI.

# Prerequisites
- A functioning [Docker](https://docs.docker.com/get-docker/) installation.
- A [FoundryVTT.com](https://foundryvtt.com/auth/register/) account with a purchased
  software license.
- A domain registered with [cloudflare](https://www.cloudflare.com/en-gb/).
- A DNS A record pointed at your public IP address.
- Ports 80 & 443 forwarded for TCP connections on your firewall.
- [GIT CLI](https://git-scm.com/) installed (For windows installation).

# Installation Steps (Windows)
1. Make a new directory.
```console
mkdir foundryvtt
```
2. Change directory to the one you just made.
```console
cd foundryvtt
```
3. Clone the repo to the new directory.
```console
git clone https://github.com/JamesWilson1996/FoundryVTT-Docker.git
```
4. Open `.env` and edit variables to match your desired setup.
```
CF_DNS_API_TOKEN = <Your CF token>
CF_EMAIL = <Your CF Email>
FOUNDRY_USERNAME = <Your foundryvtt username>
FOUNDRY_PASSWORD = <Your foundryvtt password>
FOUNDRY_ADMIN_KEY = <Set foundryvtt admin key>
FOUNDRY_URL = `foundry.YOURDOMAIN.com`
```
5. Run docker stack as a daemon.
```
docker compose up -d
```
6. Navigate to foundry.YOURDOMAIN.com and enjoy!
> [!NOTE]
> You may have to wait a couple of minutes for the DNS to propogate.

# Generating a cloudflare DNS API Token
1. Log in to [cloudflare](https://www.cloudflare.com/en-gb/) and navigate to your profile via the icon on the top right of the page.
2. On the left you will see 'API Tokens'. Select that and then on the following window select 'Create Token'
3. Under 'API token templates', select 'Edit zone DNS'.
4. Give the token a meaningful name and restrict the 'Zone resources' to the domain you want to use for foundry.
5. Continue through the next screens until you have created your token. Make sure to copy it as you only get to see this once.