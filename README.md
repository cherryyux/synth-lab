# Synth Lab

A workshop site for learning to build analog synthesizers: a nine-session curriculum, an overview of each session, sound simulators, a virtual breadboard (Workbench), a soldering game, shopping lists, a handbook, an illustrated book, video links and personal notes.

Everything is in `index.html`. It needs no build step.

## Put it online with GitHub Pages

1. Push these files to a GitHub repository (for example `synth-lab`).
2. In the repository, open **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to **Deploy from a branch**, pick the **main** branch and the **/ (root)** folder, and press **Save**.
4. After a minute the site is live at `https://<your-username>.github.io/synth-lab/`.

Without any more setup, the site works fully and saves each person's progress and notes **on their own device**.

## Turn on accounts (free, about 10 minutes)

Accounts let each person sign in and keep their progress and notes in their own account, on any device.

1. Go to <https://console.firebase.google.com>, press **Create a project**, give it a name (e.g. `synth-lab`), and finish (Google Analytics is not needed).
2. On the project page, press the **</>** (Web) icon to add a web app. Give it a name and press **Register app**. Firebase shows a `firebaseConfig = { ... }` block. Copy it.
3. Open `firebase-config.js` in this repository, replace `null` with the copied object so it reads `window.FIREBASE_CONFIG = { apiKey: "...", ... };`, and commit.
4. In Firebase, open **Build → Authentication → Get started**. Under **Sign-in method**, turn on **Email/Password** and **Google**.
5. Still in Authentication, open **Settings → Authorized domains → Add domain** and add `<your-username>.github.io`.
6. Open **Build → Firestore Database → Create database**. Pick a location close to you (e.g. `eur3`), start in **production mode**.
7. In Firestore, open the **Rules** tab, replace everything with the contents of `firestore.rules`, and press **Publish**.

Reload the site: a **Sign in** button appears at the top right. Progress someone saved on a device before signing in is copied into their account the first time they sign in.

The free Firebase plan is far more than enough for this site.
