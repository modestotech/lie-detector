# Veritas VX-9 — prank lie detector

A single static page (`index.html`). Press **Analyze**: the left half of the button gives "Not true" and the right half gives "True". Tap anywhere to reset. Keys: `Space` = not true, `Enter` = true, `Esc` = reset.

The voice trace and dB readout come from the real microphone once you allow access. Audio is only analysed live in the browser and is never recorded, stored or sent anywhere. If the mic is denied or unavailable, the trace falls back to a simulated signal. Microphone access needs HTTPS or localhost.

## Run locally

```sh
npm start      # serves on http://localhost:8080
npm run dev    # same, with auto-reload on save
```

No Node? Use `python3 -m http.server 8080` instead.

To try it on a phone on the same network, open `http://<your-pc-ip>:8080`. The screen wake lock only works over HTTPS or on localhost, so the GitHub Pages URL is the easiest way to test on a phone.

## Deploy

`.github/workflows/deploy.yml` publishes `index.html` to GitHub Pages on every push to `main`, which includes merged PRs. You can also run it by hand from the Actions tab.

One-time setup on GitHub:
1. Settings → Pages → Source: **GitHub Actions**.
2. Optional: Settings → Branches → add a rule for `main` that requires a pull request before merging, so merged PRs are the only way to deploy.
