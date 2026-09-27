# Haven — Netlify Demo

A zero-build static Netlify deployment of the Haven wellbeing-support prototype.

## Deploy

### Netlify UI
1. Open Netlify.
2. Choose **Add new project → Deploy manually**.
3. Upload this folder or the ZIP.
4. The publish directory is `.`.

### Git
Push the contents of this folder to a repository and import the repository into Netlify. No npm install or build command is required.

## Important

This package is a frontend demonstration. It uses browser-local demo state and does not send real mental-health data to a backend.

The UI deliberately labels simulated voice processing as a demo. Do not represent it as real clinical inference or production voice analysis.

## Files

- `index.html` — complete application
- `netlify.toml` — Netlify configuration
- `_headers` — security headers
