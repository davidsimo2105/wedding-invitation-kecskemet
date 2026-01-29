# Git Setup Instructions

Run these commands in your terminal to push the code to GitHub:

```bash
# Navigate to the project directory
cd /Users/lumen/Desktop/Eskuvo/WebPage_2

# Initialize git repository
git init

# Add all files
git add .

# Create initial commit
git commit -m "Initial commit: Wedding invitation for Kecskemét location"

# Add remote repository
git remote add origin https://github.com/davidsimo2105/wedding-invitation-kecskemet.git

# Rename branch to main (if needed)
git branch -M main

# Push to GitHub
git push -u origin main
```

## If you encounter permission issues:

1. Try running the commands from Terminal.app directly (not through Cursor)
2. If that doesn't work, you may need to adjust directory permissions:
   ```bash
   sudo chmod -R u+w /Users/lumen/Desktop/Eskuvo/WebPage_2
   ```

## Alternative: If git init still fails

You can create the repository on GitHub first, then clone it and copy your files:

```bash
# Clone the empty repository
cd /Users/lumen/Desktop/Eskuvo
git clone https://github.com/davidsimo2105/wedding-invitation-kecskemet.git WebPage_2_temp

# Copy all files (excluding .git)
cd WebPage_2_temp
cp -r ../WebPage_2/* .
cp -r ../WebPage_2/.* . 2>/dev/null || true

# Remove git-related files that shouldn't be copied
rm -f .git-workflow.md setup-git.sh create-version.sh merge-version-to-develop.sh

# Add, commit, and push
git add .
git commit -m "Initial commit: Wedding invitation for Kecskemét location"
git push -u origin main

# Replace the old directory
cd ..
rm -rf WebPage_2
mv WebPage_2_temp WebPage_2
```
