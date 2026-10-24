Book Author Finder
A Streamlit app that accepts pasted book titles and uses Google's Gemini Flash model to suggest authors. Results include confidence labels and notes and can be downloaded as CSV.

Note: AI matches can be incorrect, particularly for common titles, alternate editions, and lesser-known books. Verify results before relying on them.
Requirements
- Python 3.10+
- Gemini API key from Google AI Studio
Run locally
1. Create and activate a virtual environment:
   macOS/Linux
   python -m venv .venv
   source .venv/bin/activate
   Windows PowerShell
   py -m venv .venv
   .venv\\Scripts\\Activate.ps1
2. Install dependencies:
   pip install -r requirements.txt
3. Set your key.
   macOS/Linux
   export GEMINI_API_KEY="your-gemini-api-key"
   Windows PowerShell
   $env:GEMINI_API_KEY="your-gemini-api-key"
   Or create .streamlit/secrets.toml:
   GEMINI_API_KEY = "your-gemini-api-key"
   Never commit this file or publish your API key.
4. Start the app:
   streamlit run app.py
Push to GitHub
Create an empty repository on GitHub (for example, book-author-finder), then run these commands in the project folder:
git init
git add app.py README.md requirements.txt
git commit -m "Build Book Author Finder app"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/book-author-finder.git
git push -u origin main
Replace YOUR-USERNAME with your GitHub username. Complete GitHub's authentication prompt if asked.

Recommended .gitignore contents (create this as an extra local file):
.venv/
__pycache__/
.streamlit/secrets.toml
.env
Deploy on Streamlit Community Cloud
1. Push the project to GitHub.
2. Open Streamlit Community Cloud and sign in with GitHub.
3. Select Create app, then choose your repository, branch (main), and main file path (app.py).
4. In the app's Secrets / Advanced settings area, add:GEMINI_API_KEY = "your-gemini-api-key"
5. Deploy. Streamlit installs the packages listed in requirements.txt.
6. Open the app URL and test a few book titles. Use the deployment logs if startup fails.
Model
The app defaults to gemini-2.5-flash. You can change the model identifier in the sidebar if your Gemini API access supports a different model.
Files
- app.py — Streamlit UI and Gemini request
- README.md — setup and deployment guide
- requirements.txt — Python dependencies
