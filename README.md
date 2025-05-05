# klaviyo-fetch

Klaviyo's API, but using native fetch

This was created using `@hey-api` specifically the command:

```
npx @hey-api/openapi-ts  \
-i https://raw.githubusercontent.com/klaviyo/openapi/refs/heads/main/openapi/stable.json \
-o app/services/klavyio  \
-c @hey-api/client-fetch
```

Example usage:

```
    import { getEvents } from 'klaviyo-api-fetch';

    const eventsRes = await getEvents({
      headers: {
        Authorization: `Klaviyo-API-Key ${klaviyoApiKey}`,
        revision: '2025-01-15',
      },
      query: {
        'page[cursor]': nextPageToken ?? undefined,
        sort,
        filter: metricId ? `equals(metric_id,${metricId})` : undefined,
        include: ['metric', 'profile'],
        'fields[metric]': ['name'],
        'fields[event]': ['datetime', 'timestamp', 'event_properties'],
        'fields[profile]': ['email', 'first_name', 'last_name', 'phone_number'],
      },
    });
```
