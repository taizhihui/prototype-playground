# Publish Prototype to Playground

Publish a prototype HTML file to Zhi's Prototype Playground on GitHub Pages.

## Usage

When the user says something like:
- "Publish my-prototype.html as 'My Cool Prototype'"
- "Publish ~/Downloads/demo.html with my latest screenshot"
- "Add this prototype to the playground"

## Steps

1. **Get the HTML file path** from the user's request
2. **Get the prototype name** (ask if not provided)
3. **Get an optional screenshot** path (ask if they want to add one)
4. **Copy the HTML file** to `~/Desktop/prototype-playground/prototypes/`
5. **Copy the screenshot** (if provided) to `~/Desktop/prototype-playground/images/`
6. **Update prototypes.json** - add a new entry with:
   - `name`: The display name
   - `author`: "Zhi"
   - `date`: Today's date (e.g., "Mar 10")
   - `description`: Ask the user for a short description
   - `file`: The HTML filename
   - `image`: The screenshot filename (or empty string)
   - `badge`: Optional badge like "Interactive", "New", etc.
   - `tags`: Array of relevant tags

7. **Commit and push to GitHub**:
   ```bash
   cd ~/Desktop/prototype-playground
   git add -A
   git commit -m "Add prototype: [NAME]"
   git push
   ```

8. **Provide the shareable URL**:
   ```
   https://taizhihui.github.io/prototype-playground/prototypes/[FILENAME]
   ```

## Example prototypes.json entry

```json
{
  "name": "AI Agent Onboarding V2",
  "author": "Zhi",
  "date": "Mar 10",
  "description": "Exploration of the onboarding experience with AI agents",
  "file": "ai-agent-onboarding-v2.html",
  "image": "ai-agent-onboarding-v2.png",
  "badge": "New",
  "tags": ["Onboarding", "AI Agent"]
}
```

## Notes

- The playground URL is: https://taizhihui.github.io/prototype-playground/
- Always use lowercase filenames with hyphens (no spaces)
- If git push fails, try `git pull` first then push again
