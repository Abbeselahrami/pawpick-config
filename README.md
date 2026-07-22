# pawpick-config

Remote ad configuration for the **PawPick** iOS game. The app fetches
`config.json` on every launch (≤6s), so ad behaviour changes here take effect
with **no App Store update**.

Raw URL the app reads:
`https://raw.githubusercontent.com/Abbeselahrami/pawpick-config/main/config.json`

## Keys
- `ads.enabled` — master switch (false = zero ads, no consent prompts)
- `appOpenEnabled`, `bannerEnabled`, `mrecEnabled`, `interstitialEnabled` — per-format on/off
- `interstitialOnNext` — show interstitial when the player taps Next
- `appOpenId`, `bannerId`, `mrecId`, `interstitialId` — ad unit ids (swap test → real here)
- `resultNextDelaySeconds` — delay before the Next button appears (default 5)
- `minSecondsBetweenInterstitials` — global interstitial cooldown

> Validate before committing: `python3 -m json.tool config.json`
> Invalid JSON is ignored by the app (it keeps the cached/bundled config).
