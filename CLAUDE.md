# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a static web application for a Dutch family's Sinterklaas gift exchange ("lootjes trekken" / Secret Santa). The application allows family members to discover who they should buy a gift for by entering a password.

## Architecture

**Single-file application**: The entire application is contained in [lootjes.html](lootjes.html), which includes:
- HTML structure with Bootstrap 5.2.3 for styling
- Embedded JavaScript for password validation and gift assignment logic
- Base64-encoded passwords and assigned names for each participant

**Data structure**: Secret data is stored in a JavaScript object where:
- Keys are participant names
- Values contain Base64-encoded passwords and assigned gift recipients
- No backend or database - all data is client-side only

**Security model**: Basic obfuscation using Base64 encoding (not cryptographic security). Passwords and assignments are visible in the source code if inspected.

## Key Files

- [lootjes.html](lootjes.html) - Main application file
- [sinterklaas.webp](sinterklaas.webp) - Decorative image
- [sint.png](sint.png) - Additional image asset

## How to Use

**Running the application**:
```bash
# Open the HTML file directly in a browser
open lootjes.html

# Or serve with a local web server
python3 -m http.server 8000
# Then navigate to http://localhost:8000/lootjes.html
```

**Modifying participants or assignments**:
1. Edit the `secretData` object in [lootjes.html](lootjes.html#L210-L218)
2. Encode passwords and names using Base64: `btoa("PlainText")` in browser console
3. Add/remove buttons in the HTML for new/removed participants

## Important Notes

- This is a family application with personal data - treat modifications carefully
- Language is Dutch throughout the interface and content
- Maximum gift budget: €10 EUR per person
- The application is meant to be used once per year for the Sinterklaas celebration
