# Old Hub Domain Redirects

This repository contains redirect configurations for old hub domains to point to new locations.

## Structure

```
hub-redirect/
├── README.md
├── netlify.toml          # Explicit Netlify configuration
└── public/
    └── _redirects
```

## How it works

The `public/_redirects` file contains Netlify redirect rules that will redirect all traffic from the old hub domain to the Speak to AI platform.

## Current redirect

All paths (`/*`) are redirected to: **https://hi.speak-to.ai/**

## Deployment

This can be deployed to Netlify by:
1. Connecting this GitHub repository to Netlify
2. Setting the publish directory to `public/`
3. The `_redirects` file will be automatically processed by Netlify

## Usage

To modify the redirect destination, edit the URL in both:
- `public/_redirects` file
- `netlify.toml` file

## Testing

You can test this locally by:
1. Cloning the repository
2. Serving the `public/` directory with any static file server
3. The redirects will work when deployed to Netlify or other platforms that support `_redirects` files

## Current Status

- ✅ Repository connected to Netlify
- ✅ Domain hub.speak-to.ai configured
- ✅ Redirects pointing to https://hi.speak-to.ai/