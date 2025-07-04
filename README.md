# Hub Domain Path-Stripping Redirects

This repository manages intelligent redirects for the hub.speak-to.ai service, automatically stripping sub-paths and redirecting to the appropriate UID-level pages on base.prifina.com.

## Background

The hub.speak-to.ai subdomain was previously used with deep URL structures (UID/page/subpage). The service has been migrated to base.prifina.com with a simplified structure where only the UID level is preserved.

## Structure

```
old-hub-domain-redirects/
├── README.md
├── netlify.toml          # Netlify configuration with path-stripping redirects
└── public/
    └── _redirects        # Path-stripping redirect rules
```

## How path-stripping redirects work

The system automatically strips all sub-paths after the UID, redirecting users to the main UID page on the new domain.

## Current redirect behavior

**Path stripping examples:**
- `hub.speak-to.ai` → `base.prifina.com`
- `hub.speak-to.ai/user123` → `base.prifina.com/user123`
- `hub.speak-to.ai/user123/home` → `base.prifina.com/user123`
- `hub.speak-to.ai/user123/insights` → `base.prifina.com/user123`
- `hub.speak-to.ai/user123/dashboard/settings` → `base.prifina.com/user123`
- `hub.speak-to.ai/abc789/profile/edit/advanced` → `base.prifina.com/abc789`

**Target domain:** https://base.prifina.com

## Benefits of path-stripping redirects

🎯 **Simplified navigation**: Users land on the main UID page regardless of deep links  
📱 **Consistent UX**: All old complex URLs funnel to clean, simple destinations  
🔍 **SEO consolidation**: Multiple old URLs redirect to single authoritative pages  
⚡ **Reduced 404s**: No broken links from complex old URL structures  
📊 **Cleaner analytics**: Simplified tracking on the new domain  
🔗 **Future-proof**: New domain uses simpler, more maintainable URL structure  

## Technical implementation

- **301 Permanent Redirects**: Visible URL changes, SEO-friendly
- **Rule precedence**: Most specific patterns (multi-level) processed first
- **UID preservation**: First path segment (UID) is always preserved
- **Sub-path stripping**: Everything after UID is automatically removed
- **Force enabled**: Ensures redirects take precedence over any files

## Deployment

- Connected to Netlify via GitHub integration
- Auto-deploys when changes are pushed to main branch
- Publish directory: `public/`
- Domain: hub.speak-to.ai

## Usage

To modify the redirect destination domain:
1. Update `base.prifina.com` in `public/_redirects`
2. Update `base.prifina.com` in `netlify.toml`
3. Commit and push - Netlify will auto-deploy

The path-stripping logic will remain the same regardless of the destination domain.