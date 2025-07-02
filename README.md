# Old Hub Domain Redirects

This repository contains redirect configurations for old hub domains to point to new locations.

## Structure

```
hub-redirect/
└── public/
    └── _redirects
```

## How it works

The `public/_redirects` file contains Netlify redirect rules that will redirect all traffic from the old hub domain to the specified Notion page.

## Current redirect

All paths (`/*`) are redirected to: https://prifina.notion.site/About-hub-speak-to-ai-223e4a770237807988b885d158b120d5b3?pv

## Deployment

This can be deployed to Netlify by:
1. Connecting this GitHub repository to Netlify
2. Setting the publish directory to `public/`
3. The `_redirects` file will be automatically processed by Netlify

## Usage

To modify the redirect destination, edit the URL in the `public/_redirects` file.

## Testing

You can test this locally by:
1. Cloning the repository
2. Serving the `public/` directory with any static file server
3. The redirects will work when deployed to Netlify or other platforms that support `_redirects` files