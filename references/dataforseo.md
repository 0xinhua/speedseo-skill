# DataForSEO usage

Official documentation checked: 2026-10-26. Check the relevant endpoint documentation again when implementing requests; supported parameters, availability, and prices can change.

## Connection and credentials

- Prefer an available DataForSEO connector or MCP tool. Its configured credentials may differ from credentials supplied by the user; do not claim it uses the supplied account unless its configuration establishes that.
- If no suitable tool is connected, use direct HTTPS requests when the runtime has network access and credentials are available. Missing MCP tools alone do not make DataForSEO unavailable.
- Obtain **API Login** and **API Password** from [API Access](https://app.dataforseo.com/api-access). The API Password is different from the dashboard password.
- Authentication is HTTP Basic: `Authorization: Basic <base64(login:password)>`. It is not Bearer authentication and needs no separate token exchange. See [authentication](https://docs.dataforseo.com/v3/auth/).
- If the user says “API Key,” establish whether they supplied the login/password pair or an already encoded Basic credential. Do not guess a missing login, use a dashboard password, or encode an already encoded credential a second time.
- Prefer runtime secrets or `DATAFORSEO_LOGIN` and `DATAFORSEO_PASSWORD` environment variables. These variable names are a convention for these examples; the API itself receives an Authorization header. A local `.env` is not loaded automatically and must be excluded from Git if used.
- Use supplied credentials only for the requested DataForSEO work. Never echo credentials, put them in URLs, commit them, or save them in research records, source code, article output, or request logs. Base64 credentials are secrets too. Save response bodies and non-secret request parameters, not Authorization headers. Redact secrets from errors before sharing them.

## Research requests

Use the endpoint that matches the required evidence rather than assuming one response supplies all metrics.

| Evidence | Endpoint | Documentation |
| --- | --- | --- |
| Google organic results, returned PAA and AI Overview items | `POST /v3/serp/google/organic/live/advanced` | [SERP Live Advanced](https://docs.dataforseo.com/v3/serp/google/organic/live/advanced/) |
| Google Ads keyword search volume and returned advertising metrics | `POST /v3/keywords_data/google_ads/search_volume/live` | [Search Volume Live](https://docs.dataforseo.com/v3/keywords_data/google_ads/search_volume/live/) |
| Account information for connection diagnosis when needed | `GET /v3/appendix/user_data` | [User Data](https://docs.dataforseo.com/v3/appendix/user_data/) |

- Use the requested region and language; resolve supported location/language values from the relevant API documentation. Record device for SERP requests. Do not silently substitute a different market.
- Live POST bodies are arrays of task objects. For SERP, include `keyword` and the selected location/language. For search volume, include `keywords` and the selected location/language. Read endpoint-specific limits before batching.
- Advertising competition is not organic SEO difficulty. Preserve metric names, units, source, and retrieval date; treat null or absent metrics as unavailable.
- PAA and AI Overview evidence depends on what was actually returned. Record absent, pending, or empty items accurately and read returned reference pages before citing their contents.
- Requests may incur charges. Use the requested scope and any user budget, reuse saved responses, and avoid repeated Live calls or optional paid expansions. Consult [current pricing](https://dataforseo.com/pricing) rather than hard-coding prices. Supplying credentials does not authorize unrelated queries or account/billing changes.

## Responses and failures

- Check HTTP status, top-level `status_code`, each task's `status_code`/`status_message`, and actual `result` contents. HTTP 200 alone does not establish task success; see [API errors](https://docs.dataforseo.com/v3/appendix/errors/).
- A completed task normally has status `20000`; inspect returned data before treating it as useful evidence. For asynchronous task endpoints, keep task IDs and retrieve the results using the matching task-get endpoint. A queued task is not retrieved research.
- Save raw response bodies with retrieval date and non-secret request parameters in the target project's research location. Record task IDs, returned cost, and unavailable evidence when present.
- On authentication, balance, permission, or parameter errors, identify and correct the specific issue. Do not retry the same invalid request indefinitely. After a timeout, check available task status before resubmitting potentially billable work.
- If requests remain unavailable, record the blocker and stop drafting unless the user authorizes an alternative source.
