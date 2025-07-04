# Hub Domain Dynamic Redirects

This repository manages dynamic redirects for the hub.speak-to.ai service, preserving the original URL structure while pointing to the new base.prifina.com domain.

## Background

The hub.speak-to.ai subdomain was previously used for a service with multiple URLs and endpoints. The service has been migrated to base.prifina.com, and all traffic now dynamically redirects to preserve the original URL structure.

## Structure

```
old-hub-domain-redirects/
├── README.md
├── netlify.toml          # Netlify configuration with dynamic redirects
└── public/
    └── _redirects        # Dynamic redirect rules
```

## How dynamic redirects work

Instead of redirecting everything to a single page, this setup preserves the original URL structure by redirecting each path to the corresponding path on the new domain.

## Current redirect behavior

**Dynamic path preservation:**
- `hub.speak-to.ai` → `base.prifina.com`
- `hub.speak-to.ai/login` → `base.prifina.com/login`
- `hub.speak-to.ai/dashboard` → `base.prifina.com/dashboard`
- `hub.speak-to.ai/api/users/123` → `base.prifina.com/api/users/123`
- `hub.speak-to.ai/any/deep/path` → `base.prifina.com/any/deep/path`

**Target domain:** https://base.prifina.com

## Benefits of dynamic redirects

🔗 **Preserves functionality**: Users land on the equivalent page on the new domain  
📱 **Better user experience**: No confusion about where content moved  
🔍 **SEO-friendly**: 301 redirects maintain search engine rankings for specific pages  
⚡ **Seamless migration**: Existing bookmarks and links continue to work  
📊 **Analytics preservation**: Each page redirect can be tracked individually  

## Technical implementation

- **301 Permanent Redirect**: Informs search engines the content has permanently moved
- **`:splat` parameter**: Captures the entire path and preserves it in the redirect
- **Force redirect**: Ensures the redirect takes precedence over any files
- **Wildcard matching**: `/*` catches all possible URLs under the domain

## Deployment

- Connected to Netlify via GitHub integration
- Auto-deploys when changes are pushed to main branch
- Publish directory: `public/`
- Domain: hub.speak-to.ai

## Usage

To modify the redirect destination:
1. Update the URL in `public/_redirects` (change `base.prifina.com` to new domain)
2. Update the URL in `netlify.toml` (change `base.prifina.com` to new domain)
3. Commit and push - Netlify will auto-deploy

This ensures a seamless migration where all existing URLs continue to work on the new domain structure.