# Zingsentek GitHub Pages

Static website for app support pages, privacy policies, and store listings.

## CRITICAL: Store Compliance

These pages are directly linked from App Store Connect and Google Play Console metadata (Privacy Policy URL, Support URL). Any changes can impact app review and store listing status.

- NEVER add content that violates Apple App Store Review Guidelines or Google Play Developer Policies
- NEVER include misleading claims, false advertising, or deceptive content
- NEVER add content that could be illegal in any jurisdiction worldwide
- Privacy policies MUST accurately reflect actual app data collection and usage
- Privacy policies MUST comply with GDPR (EU), CCPA (California), COPPA (children), PDPA, LGPD, and all applicable data protection laws
- Support pages MUST provide a working contact method
- Do NOT remove or break privacy policy or support URLs - this will cause store rejection
- Do NOT add gambling, adult, or restricted content references
- Do NOT make health/medical claims without proper disclaimers
- All content must be truthful, legally defensible, and appropriate for a global audience

## Project Structure

```
index.html                              # Home page (English only)
style.css                               # Shared stylesheet (includes RTL support)
app-ads.txt                             # App advertising configuration
privacy-policy/
  <app-slug>.html                       # English (base)
  es/<app-slug>.html                    # Spanish
  fr/<app-slug>.html                    # French
  <lang>/<app-slug>.html                # Other languages
support/
  <app-slug>.html                       # English (base)
  es/<app-slug>.html                    # Spanish
  fr/<app-slug>.html                    # French
  <lang>/<app-slug>.html                # Other languages
```

## Apps

| App | Bundle ID | App Store | Google Play |
|-----|-----------|-----------|-------------|
| Zingsentek Travel App | com.shebin.zingsentek | Yes | Yes |
| Yolk Slam | com.shebin.eggthrow | Yes | Yes |
| Spot it - swipe | com.shebin.SwipeMatch | Yes | No |
| Easy peasyy Stopwatch | com.shebin.SSStopwatch | Yes | No |
| Connecting Dots - Multiplayer | com.shebin.ConnectingDot | Yes | No |
| Duplicate Contacts Finder | com.shebin.koshy.SSContactCleaner | Yes | No |

## Localization

### Supported Languages
en, es, zh-Hans, ja, fr, de, pt, ko, it, ru, ar, hi, id, tr, zh-Hant, nl, pl, vi, th, ms, sv, da, no, tl, fil

### Language Codes (directory names)
es, zh-Hans, ja, fr, de, pt, ko, it, ru, ar, hi, id, tr, zh-Hant, nl, pl, vi, th, ms, sv, da, no, tl, fil

### Localization Architecture
- Base pages (English) live at: `privacy-policy/<app-slug>.html`, `support/<app-slug>.html`
- Localized pages use lang subdirectories: `privacy-policy/<lang>/<app-slug>.html`
- Stylesheet path from localized pages: `../../style.css` (two levels up)
- `index.html` remains English-only (not linked from store metadata)
- Each localized page must set `<html lang="<code>">` correctly
- RTL languages (ar) must include `dir="rtl"` on the `<html>` tag
- All pages include `<link rel="alternate" hreflang="...">` tags for each available language
- Breadcrumb includes a language switch link (e.g., "English" on Spanish pages, "Español" on English pages)
- Cross-links within localized pages must point to the same language (e.g., Spanish support links to Spanish privacy policy)
- When adding a new language, add it for ALL apps, not selectively
- Translations must be professional quality - no machine-translated legal text without review

### Implemented Languages
- **All 25 languages** - All 6 apps (en, es, fr, de, pt, it, nl, ja, ko, zh-Hans, zh-Hant, ru, pl, sv, da, no, ar, hi, id, tr, vi, th, ms, tl, fil)
- English base pages include hreflang tags for all 25 languages

### Reference Implementation
See `privacy-policy/fr/` and `support/fr/` for the complete reference pattern (all 6 apps localized).

## Conventions

- All pages use `style.css` as the shared stylesheet (linked via `../style.css` or `../../style.css` from subfolders)
- Store badges use official Apple and Google badge images (not text links)
- App Store badge: `https://developer.apple.com/assets/elements/badges/download-on-the-app-store.svg`
- Google Play badge: `https://play.google.com/intl/en_us/badges/static/images/badges/en_badge_web_generic.png`
- Only add Google Play badge for apps that are actually published on Google Play
- Each app has both a privacy policy and support page
- Contact email: shebinkoshyios@gmail.com
- Website: zingsentek.web.app

## When Adding a New App

1. Add an app card in `index.html` inside the `.app-grid` div
2. Create `privacy-policy/<app-slug>.html`
3. Create `support/<app-slug>.html`
4. Create localized versions in `privacy-policy/<lang>/<app-slug>.html` for all supported languages
5. Create localized versions in `support/<lang>/<app-slug>.html` for all supported languages
6. Only include store badges for stores where the app is published
7. Update the Apps table in this file

## When Adding a New Language

1. Create `privacy-policy/<lang>/` and `support/<lang>/` directories
2. Add translated pages for ALL apps
3. Add `hreflang` link tags to all existing pages pointing to the new translations
4. For RTL languages, ensure `dir="rtl"` is set
5. Update the supported languages list in this file
