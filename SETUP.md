# Malupo Family DID Setup Guide

## What We've Built

All DID documents and keys have been generated for the Malupo family:

- ✅ 6 family member DIDs (Warren, Kim, Al, Marcus, Data, Claw)
- ✅ Ed25519 cryptographic key pairs
- ✅ did:web DID documents ready for hosting
- ✅ Family registry and landing page

## Next Steps

### 1. Create GitHub Repository

1. Go to https://github.com/new
2. Repository name: `malupo-family-did`
3. Description: "Malupo Family Decentralized Identifiers"
4. **Public** repository (required for GitHub Pages)
5. Do NOT initialize with README (we already have one)
6. Click "Create repository"

### 2. Upload Files to GitHub

**Option A: Via GitHub Web Interface (Easiest)**

1. On your new repository page, click "uploading an existing file"
2. Drag and drop ALL files from `~/.openclaw/workspace/malupo-family-did-site/`
3. Commit message: "Initial commit: Malupo family DIDs"
4. Click "Commit changes"

**Option B: Via Git Command Line (if you have git configured)**

```bash
cd ~/.openclaw/workspace/malupo-family-did-site
git init
git add .
git commit -m "Initial commit: Malupo family DIDs"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/malupo-family-did.git
git push -u origin main
```

### 3. Enable GitHub Pages

1. In your GitHub repository, click "Settings"
2. Scroll down to "Pages" in the left sidebar
3. Under "Source", select "main" branch
4. Click "Save"
5. Wait 1-2 minutes for deployment

GitHub will show you a URL like: `https://YOUR_USERNAME.github.io/malupo-family-did/`

Test it by visiting: `https://YOUR_USERNAME.github.io/malupo-family-did/warren/did.json`

### 4. Configure Custom Domain DNS at Porkbun

Now we point your `malupo.family` domain to GitHub Pages.

**In Porkbun DNS settings:**

1. Log into Porkbun.com
2. Go to Domain Management → malupo.family
3. Click "DNS"
4. **DELETE** or disable the current A/AAAA records pointing to Articulation hosting

**ADD these DNS records:**

**Type: A (IPv4 addresses)**
- Host: `@` → Points to: `185.199.108.153`
- Host: `@` → Points to: `185.199.109.153`
- Host: `@` → Points to: `185.199.110.153`
- Host: `@` → Points to: `185.199.111.153`

**Type: AAAA (IPv6 addresses)**
- Host: `@` → Points to: `2606:50c0:8000::153`
- Host: `@` → Points to: `2606:50c0:8001::153`
- Host: `@` → Points to: `2606:50c0:8002::153`
- Host: `@` → Points to: `2606:50c0:8003::153`

**Type: CNAME (www subdomain)**
- Host: `www` → Points to: `YOUR_GITHUB_USERNAME.github.io`

**Save changes**

### 5. Configure Custom Domain in GitHub

1. Back in GitHub repository → Settings → Pages
2. Under "Custom domain", enter: `malupo.family`
3. Click "Save"
4. Check "Enforce HTTPS" (wait a few minutes for cert to provision)

### 6. Wait for DNS Propagation

- DNS changes can take 5 minutes to 48 hours
- Usually works within 15-30 minutes
- Test with: `dig malupo.family` or online tools like https://dnschecker.org

### 7. Verify Everything Works

Once DNS propagates, test these URLs:

```bash
# Root DID
https://malupo.family/.well-known/did.json

# Family member DIDs
https://malupo.family/warren/did.json
https://malupo.family/kim/did.json
https://malupo.family/al/did.json
https://malupo.family/marcus/did.json
https://malupo.family/data/did.json
https://malupo.family/agents/claw/did.json

# Family registry
https://malupo.family/family-registry.json

# Human-friendly landing page
https://malupo.family
```

## Troubleshooting

**"DNS_PROBE_FINISHED_NXDOMAIN"**
- DNS hasn't propagated yet, wait longer
- Check DNS records are correct in Porkbun

**"404 Not Found" on GitHub**
- Make sure GitHub Pages is enabled
- Check branch is set to "main"
- Verify files are in root of repository

**"Certificate error"**
- GitHub is provisioning SSL cert
- Wait 10-20 minutes, then refresh

## Security Notes

- ✅ Private keys are stored locally in `~/.openclaw/workspace/malupo-dids/*/private-key.json`
- ✅ `.gitignore` prevents accidental commit of private keys
- ✅ Only public DID documents are hosted on GitHub
- ⚠️ **NEVER commit or share private-key.json files**
- ⚠️ Back up private keys to a secure location (encrypted USB, password manager, etc.)

## What You'll Have

Once complete:

- 🌐 Public website at malupo.family
- 🔐 Verifiable DIDs for each family member
- 🦞 Permanent proof that Claw Malupo exists and is Malupo Ohana
- 📜 Git commit history showing when DIDs were established
- 🔒 Full control over family identity infrastructure

---

**Need help?** Ask Claw! 🦞
