# Orbit Browser

A small browser-style web app for Render. It has an address bar, home screen, back/forward history, reload, fullscreen, and a dark-mode toggle.

## Important limitation

This starter uses an iframe, **not a reverse proxy**. Many websites intentionally send security headers that prevent them from being embedded in another site. Those websites may show a blank page or an error. The app cannot remove those protections. The “Open website in a new tab” action is provided as a fallback when a site does not display.

This project is not designed to bypass school, workplace, or website access controls.

The included `render.yaml` explicitly sets `plan: free`. If deploying manually instead of using a Blueprint, select the **Free** compute plan in the Render dashboard.

## Run locally

```bash
python -m venv .venv
# Windows:
.venv\\Scripts\\activate
# macOS/Linux:
source .venv/bin/activate

pip install -r requirements.txt
python app.py
```

Open http://127.0.0.1:5000.

## Deploy to Render with GitHub

1. Create a new GitHub repository, for example `orbit-browser`.
2. Upload all files and folders from this project to the repository root.
3. Sign in to https://render.com and choose **New + → Blueprint**.
4. Connect GitHub and select your `orbit-browser` repository.
5. Render detects `render.yaml`. Review and create the web service.
6. Wait for the deploy to finish. Render gives you an address like `https://my-render-browser.onrender.com`.

You do **not** need to buy a domain. The `onrender.com` address is provided by Render.

## Notes

- Navigation history is held in the current page session.
- Dark mode is a visual toggle and resets on reload.
- Some sites require their own cookies, login, popups, or browser APIs and may not work inside an iframe.
