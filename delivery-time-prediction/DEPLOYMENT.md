# How to Deploy This App on Streamlit Community Cloud

Step-by-step guide to get this app live with **your name** on it.

---

## Step 1 — Upload the project to YOUR GitHub

1. Log in to [github.com](https://github.com) with **your** account.
2. Click the **+** icon (top-right) → **New repository**.
3. Repository name: `delivery-time-prediction` (or any name you like).
4. Choose **Public** (required for the free Streamlit Community Cloud).
5. Do NOT tick "Add a README" (the project already has one).
6. Click **Create repository**.
7. On the new repo page, click **uploading an existing file** link.
8. Drag and drop **ALL files and folders** from this project
   (`app`, `data`, `models`, `notebooks`, `reports`, `src`, `tests`,
   `.streamlit`, `.gitignore`, `README.md`, `requirements.txt`,
   `DEPLOYMENT.md`) into the upload area.
   - Make sure `models/best_model.joblib`, `models/lgbm_q10.pkl`,
     `models/lgbm_q90.pkl`, and `models/categories.json` are included —
     the app cannot start without them.
   - Data files are ~6 MB, well under GitHub's limits.
9. Wait for all files to finish uploading, then click **Commit changes**.

> Tip: if you prefer the command line:
> ```bash
> git init
> git add .
> git commit -m "Delivery time prediction project"
> git branch -M main
> git remote add origin https://github.com/<YOUR-USERNAME>/delivery-time-prediction.git
> git push -u origin main
> ```

---

## Step 2 — Deploy on Streamlit Community Cloud

1. Go to [share.streamlit.io](https://share.streamlit.io) and click **Sign up**
   → choose **Continue with GitHub** → authorize Streamlit with **your**
   GitHub account.
2. Once inside your workspace, click **Create app** (top-right) →
   **Paste GitHub URL** (or "Deploy a public app from GitHub").
3. Fill in the three fields:
   - **Repository:** `YOUR-USERNAME/delivery-time-prediction`
   - **Branch:** `main`
   - **Main file path:** `app/streamlit_app.py`  ← important!
4. (Optional but recommended) Click **Advanced settings** and pick a
   **Custom subdomain**, e.g. `yourname-delivery-eta` —
   your app will live at `https://yourname-delivery-eta.streamlit.app`.
5. Click **Deploy**.
6. First build takes ~5–10 minutes (Streamlit installs
   `requirements.txt` and boots the app). Watch the logs; when it says
   "Your app is live", you are done.

---

## Where YOUR name shows up

| Place | What appears |
|-------|--------------|
| App URL | `https://<your-subdomain>.streamlit.app` (your chosen subdomain) |
| Streamlit workspace | App listed under **your** account with your profile picture |
| GitHub repo | `github.com/YOUR-USERNAME/delivery-time-prediction` — your avatar, your contribution graph |
| App footer (optional) | Edit the last `st.caption(...)` in `app/streamlit_app.py` to add e.g. "Built by YOUR NAME" |

---

## Updating the app later

Any change you push to the `main` branch of the GitHub repo is picked up
automatically — Streamlit rebuilds the app within a minute or two.
No redeploy needed.

## Troubleshooting

| Problem | Fix |
|---------|-----|
| "Could not load models or data" on the app | The 4 files in `models/` are missing from the repo — upload them and push again. |
| Build fails on a package | Make sure `requirements.txt` is in the repo root. |
| App sleeps after inactivity | Normal on the free tier — it wakes on the next visit. |
| Module not found error | The package is missing from `requirements.txt` — add it and push. |

---

## Credits

Original project idea and model training pipeline by
[anshalanjewar](https://github.com/anshalanjewar/delivery-time-prediction).
