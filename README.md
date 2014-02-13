# Webhooked Wiki

Github Webhooks + Cloudant

## Thus far...

At Cloudant.com:
1. created a `webhooked-wiki` database in `labs.cloudant.com`
2. generated an API Key & Secret (kept a copy of both for later use)
3. changed that API Key's permission from "Reader" to "Writer" (only)

At Github.com:
1. created this repo
2. went to `Settings | Webhooks & Services` for the repo & added a webhook to `POST`
to `https://API_KEY:API_SECRET@labs.cloudant.com/webhooked-wiki`
3. set the "Payload version" dropdown to `application/vnd.github.v3+json`
4. set it to "Send me **everything**."
5. saved it.
6. reloaded the `Webhooks & Services` page and was happy to see a green checkmark
showing that the webhook succeeded.

Back at Cloudant.com:
1. checked the contents of the DB which now contained this document

```javascript
{
  "_id": "48117e624b7c7046321a91d7d9458466",
  "_rev": "1-1b43993ced1056aba9cdb3e3b05be0e5",
  "zen": "Anything added dilutes everything else.",
  "hook_id": 1808374
}
```
