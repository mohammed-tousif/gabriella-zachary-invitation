# Digital Invitations

Single-file, animated digital invitation sites. Each event lives in its own folder/branch and deploys to its own Vercel project, so they're independent — updating one never touches another.

## Live deployments

| Event | Live link | Source | Branch |
|---|---|---|---|
| Sumera & Hayat — Nikah | [gabriella-zachary.vercel.app](https://gabriella-zachary.vercel.app) | [`index.html`](index.html) | `master` |
| Mohammed Yusuf — Chilla Ceremony | [chilla-mohammed-yusuf.vercel.app](https://chilla-mohammed-yusuf.vercel.app) | [`chilla-mohammed-yusuf/index.html`](chilla-mohammed-yusuf/index.html) | `chilla-mohammed-yusuf` (not merged to `master`) |
| Nikhath & Abdul Jabbar — Engagement | [invitation-from-kazi-family.vercel.app](https://invitation-from-kazi-family.vercel.app) | [`nikhath-abduljabbar/index.html`](nikhath-abduljabbar/index.html) | `nikhath-abduljabbar` (not merged to `master`) |

## Structure

```
.
├── index.html                     # Sumera & Hayat (root site, master branch)
├── chilla-mohammed-yusuf/
│   └── index.html                 # Mohammed Yusuf Chilla Ceremony (own branch + Vercel project)
└── nikhath-abduljabbar/
    └── index.html                 # Nikhath & Abdul Jabbar Engagement (own branch + Vercel project)
```

Each `index.html` is fully self-contained — HTML, CSS, and JS in one file, with fonts and GSAP/ScrollTrigger pulled from CDN. No build step.

## Running locally

Any static file server works, e.g.:

```bash
python -m http.server 8791
```

Then open `http://localhost:8791/` for Sumera & Hayat, or `http://localhost:8791/chilla-mohammed-yusuf/` for the Chilla ceremony site.

## Deploying

Each site is a separate Vercel project, deployed from its own directory:

```bash
# Sumera & Hayat — from repo root
vercel --prod

# Mohammed Yusuf Chilla Ceremony — from its own folder
cd chilla-mohammed-yusuf && vercel --prod

# Nikhath & Abdul Jabbar Engagement — from its own folder
cd nikhath-abduljabbar && vercel --prod
```

New events should follow the same pattern: a new folder + a new branch (reviewed before merging to `master`) + a new Vercel project rooted at that folder.
