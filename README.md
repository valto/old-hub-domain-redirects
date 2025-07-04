# Hub Domain Redirects

This repository manages redirects for the discontinued hub.speak-to.ai service.

## Background

The hub.speak-to.ai subdomain was previously used for a service with multiple URLs and endpoints. The service has been discontinued, and all traffic from this domain now redirects to documentation explaining the transition.

## Structure

```
old-hub-domain-redirects/
├── README.md
├── netlify.toml          # Explicit Netlify configuration
└── public/
    └── _redirects
```

## How it works

All traffic from hub.speak-to.ai (including all subpaths) is redirected to a Notion documentation page that explains:
- What happened to the hub service
- What users can do instead
- Where to find alternative solutions

## Current redirect behavior

**All paths redirect to the same destination:**
- `hub.speak-to.ai` → Notion documentation
- `hub.speak-to.ai/login` → Notion documentation  
- `hub.speak-to.ai/dashboard` → Notion documentation
- `hub.speak-to.ai/any/path` → Notion documentation

**Destination:** https://prifina.notion.site/About-hub-speak-to-ai-223e4a7702378079b885d158b120d5b3

## Technical implementation

- **301 Permanent Redirect**: Informs search engines the content has permanently moved
- **Wildcard matching**: `/*` catches all possible URLs under the domain
- **Force redirect**: Ensures the redirect takes precedence over any files

## Deployment

- Connected to Netlify via GitHub integration
- Auto-deploys when changes are pushed to main branch
- Publish directory: `public/`
- Domain: hub.speak-to.ai

## Usage

To modify the redirect destination:
1. Update the URL in `public/_redirects`
2. Update the URL in `netlify.toml` 
3. Commit and push - Netlify will auto-deploy

This ensures users who bookmarked or linked to the old hub service get proper information about the transition instead of broken links.