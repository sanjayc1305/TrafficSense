# Push to GitHub - Step by Step Instructions

## Current Issue
You're authenticated as `kartick026` but need to push to `sanjayc1305/TrafficSense` repository.

## Solution: Use Personal Access Token

### Step 1: Create Personal Access Token
1. Go to: **https://github.com/settings/tokens**
2. Click **"Generate new token"** → **"Generate new token (classic)"**
3. Give it a name: `TrafficSense Push`
4. Select expiration: `90 days` (or your preference)
5. Check the scope: **`repo`** (this gives full repository access)
6. Click **"Generate token"**
7. **IMPORTANT**: Copy the token immediately (you won't see it again!)
   - It will look like: `ghp_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx`

### Step 2: Push with Token
Run these commands in PowerShell:

```powershell
cd d:\downloads\trafficsense

# Push (it will prompt for credentials)
git push -u origin main --force
```

**When prompted:**
- **Username**: `sanjayc1305`
- **Password**: `<paste your personal access token here>` (NOT your GitHub password)

### Alternative: Use Token in URL (One-time)

If you prefer, you can embed the token in the URL:

```powershell
cd d:\downloads\trafficsense

# Replace YOUR_TOKEN with your actual token
git remote set-url origin https://YOUR_TOKEN@github.com/sanjayc1305/TrafficSense.git

# Then push (no prompt needed)
git push -u origin main --force
```

### Step 3: Verify Push
After pushing, check: **https://github.com/sanjayc1305/TrafficSense**

You should see all your files there!

## Security Note
⚠️ The token in the URL method is less secure. Better to use the credential prompt method.

## If Push Still Fails

1. **Check Repository Access**: Make sure you have push access to `sanjayc1305/TrafficSense`
2. **Try SSH Instead**:
   ```powershell
   git remote set-url origin git@github.com:sanjayc1305/TrafficSense.git
   git push -u origin main --force
   ```
3. **Verify You're Owner/Collaborator**: Check repository settings

