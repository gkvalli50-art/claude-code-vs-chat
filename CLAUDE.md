# Claude Code vs Claude Chat — Project Notes

## Project Overview
A single-page HTML site comparing Claude Code and Claude Chat, deployed on GitHub and Vercel.

---

## Project Structure
```
Claude vercel deployment/
├── index.html      # Main comparison page (dark editorial aesthetic)
├── vercel.json     # Vercel static deployment config
└── CLAUDE.md       # This file
```

---

## Steps Taken to Build & Deploy

### 1. Created the HTML Page
- Single `index.html` file with no external JS dependencies
- Fonts loaded from Google Fonts: Bebas Neue, DM Mono, Lora, Instrument Sans
- Sections: Split hero, overview cards, comparison table, feature grid, decision guide, footer
- Scroll reveal via IntersectionObserver API
- Fully responsive (mobile breakpoints at 900px and 600px)

### 2. Initialized Git Repository
```bash
git init
git config user.email "yohenthiran@users.noreply.github.com"
git config user.name "Yohenthiran"
git add index.html
git commit -m "Add Claude Code vs Claude Chat comparison page"
```

### 3. Installed Node.js & Vercel CLI
- Node.js was not installed — installed via winget:
```bash
winget install OpenJS.NodeJS.LTS --accept-source-agreements --accept-package-agreements
```
- Installed Vercel CLI globally:
```bash
npm install -g vercel
```
- Node path for this machine: `C:\Program Files\nodejs`
- npm global bin: `C:\Users\Yohenthiran\AppData\Roaming\npm`

### 4. Deployed to Vercel
- Vercel account: `gkvalli50-6013s-projects` (team ID: `team_qCeMQuB1WFpwss4OD4DYkean`)
- Created `vercel.json` with `@vercel/static` build config
- Deployed using:
```bash
export PATH="/c/Program Files/nodejs:/c/Users/Yohenthiran/AppData/Roaming/npm:$PATH"
vercel deploy --prod --yes --token <VERCEL_TOKEN> --scope gkvalli50-6013s-projects
```
- **Live URL:** https://claude-code-vs-chat-ten.vercel.app
- **Vercel project:** `gkvalli50-6013s-projects/claude-code-vs-chat`

### 5. Pushed to GitHub
- GitHub account: `gkvalli50-art`
- Repo: https://github.com/gkvalli50-art/claude-code-vs-chat
- Push command (used a classic PAT with `repo` scope):
```bash
git remote add origin https://github.com/gkvalli50-art/claude-code-vs-chat.git
git branch -M main
git push -u origin main
```

---

## Future Deployments

To redeploy after changes:
```bash
export PATH="/c/Program Files/nodejs:/c/Users/Yohenthiran/AppData/Roaming/npm:$PATH"
cd "C:/Users/Yohenthiran/OneDrive/Documents/Claude vercel deployment"

# Deploy to Vercel
vercel deploy --prod --yes --token <VERCEL_TOKEN> --scope gkvalli50-6013s-projects

# Push to GitHub (set remote URL with token or use stored credentials)
git add .
git commit -m "your message"
git push origin main
```

## To install Vercel CLI on a new session
```bash
export PATH="/c/Program Files/nodejs:/c/Users/Yohenthiran/AppData/Roaming/npm:$PATH"
vercel --version   # confirm it's available
```

---

## Notes
- `gh` CLI is **not installed** on this machine — GitHub operations must use git + PAT token or the API via curl
- Vercel CLI auth.json is at: `C:\Users\Yohenthiran\AppData\Roaming\com.vercel.cli\Data\auth.json`
- The Vercel MCP tool (`deploy_to_vercel`) is available in Claude Code but requires `.vercel/project.json` to be present before it can deploy
- Do **not** commit the `.vercel/` directory or any token values to the repository
