# FoundryVTT-Docker
A setup for using Felddy's docker image for FoundryVTT with traefik. All settings configured using the .env file.
Steps are written assuming no prior knowledge of using CLI.

# Prerequisites
- A functioning [Docker](https://docs.docker.com/get-docker/) installation.
- A [FoundryVTT.com](https://foundryvtt.com/auth/register/) account with a purchased
  software license.
- A domain registered with [cloudflare](https://www.cloudflare.com/en-gb/).
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
```
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