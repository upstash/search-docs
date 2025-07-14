## Description

A modern documentation library to search and track the docs.

## Getting Started

First, run the development server:

```bash
npm install
npm run dev
```

## How it Works
- Search: Uses Upstash Search UI to query multiple indexes in parallel, sorts and groups results, and displays them with section headers.
- Recent Updates: Upstash Qstash fetches all documents from multiple indexes in batches, filters for those crawled in the last 24 hours.

## Set the Crawler

- Import the crawler function and call it with the required credentials
- Deploy this functionality to vercel and call it using Qstash Schedule
providing the index name and the url of the docs in the body.
- It will crawl and upsert the data to Upstash Search on schedule.

```
import { crawlAndIndex } from "@upstash/search-crawler"

export async function crawlDocumentation(request) {

    result = await crawlAndIndex({
      upstashUrl,
      upstashToken,
      indexName: request.indexName,
      docUrl: request.docsUrl,
    })
}

```

## Conclusion
Finally, the UI will make use of these components to serve users to find whatever they want from 
any source they want. Moreover, they can keep up with the updates in their favorite docs.


