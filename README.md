# teamfastfoundation.makeacompany.ai

Rebuild of [teamfastfoundation.com](https://teamfastfoundation.com/) — veteran reintegration nonprofit, Camp Victor as the flagship program. Hosted at https://teamfastfoundation.makeacompany.ai.

A lightweight static one-pager built to the IA most-trusted military-support nonprofits use: persistent crisis line, transparent governance, clear program structure, tiered donations with impact framing, and multiple paths to involvement.

## Stack

- `index.html` — vanilla HTML/CSS, Google Fonts (Inter + Fraunces), schema.org NGO JSON-LD.
- `Dockerfile` — `nginx:1.27-alpine` + the file.
- `.github/workflows/build.yml` — builds and pushes `geeemoney/teamfastfoundation:<version>` on tag.
- Cluster manifests live in [`BimRoss/rancher-admin`](https://github.com/BimRoss/rancher-admin) under `admin/apps/teamfastfoundation/`.

## Releasing

```sh
git tag -a v0.1.0 -m "v0.1.0"
git push origin v0.1.0
```

Tag push builds the image and auto-opens a gitops PR against `rancher-admin` to bump `admin/apps/teamfastfoundation/deployment.yaml`.

## TBD before this is donor-ready

- 501(c)(3) EIN, IRS letter, GuideStar / Charity Navigator links
- Board roster (names, photos, military backgrounds)
- Most recent Form 990 and annual report PDFs
- Real Camp Victor dates, location, and photo gallery
- Verified social handles
- Real contact info (address, phone, mailing) replacing the `@teamfastfoundation.com` placeholders
- Newsletter integration (Mailchimp, Beehiiv, or similar)
- Production donation flow (Stripe + DAF + employer match) replacing the PayPal-only fallback
