## CouchDB image for Self-hosted LiveSync with Tailscale funnel 

### What is this
- CouchDB Server which configured about CORS for Obsidian and Self-hosted LiveSync.
- Instead of using your SSL Certificate or Domains, Using [tailScale](https://tailscale.com/) funnel.

### Prerequisites
- You should have an account of tailscale.
- Your tailscale account should enabled funnel once.

(To more instructions, read the [official document](https://tailscale.com/blog/docker-tailscale-guide)).

### How to use
- Rename `.env.couchdb.sample` to `.env.couchdb`.
- Fill [your-favourite-user-name] and [and-your-favourite-password] in `.env.couchdb`.
- Rename `.env.tailscale-app.sample` to `.env.tailscale-app`.
- Fill [HERE_FOR_YOUR_TAILSCALE_AUTHKEY] in `.env.tailscale-app`.
  - Note: This should be `OAuth` key.
- run `docker compose up`


Note: If you are first to this, some interaction will be shown. Please follow messages. And if you have been simply failed, please run `docker exec -it  tailscale_couchdb-tailscale-app tailscale funnel 5984` from the other terminal. The message like following will be shown.

```
docker exec -it  tailscale_couchdb-tailscale-app  tailscale funnel 5984

Funnel is enabled, but the list of allowed nodes in the tailnet policy file does not include the one you are using.
To give access to this node you can edit the tailnet policy file, or visit:

         https://login.tailscale.com/f/funnel?node=something random

```

And, if you have completed the configuration, following will also be shown.

```
Success.
Available on the internet:

https://xxxxxxxxxx.xxxxxxx.ts.net/
|-- proxy http://127.0.0.1:5984
```
