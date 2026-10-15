# Setting up My Money

About 10 minutes. It uses the same Firebase project and login as My Planner, and your Firebase details are already filled in.

## 1. Update the Firestore rules

The old rules only allowed the planner's data, so this step lets My Money save too.

1. Go to **console.firebase.google.com** → your project → **Firestore Database → Rules**.
2. Delete everything there, paste in the contents of `firestore.rules` from this folder, and click **Publish**.

If you locked the rules to your own UID earlier, change the line to:
`allow read, write: if request.auth != null && request.auth.uid == uid && uid == "YOUR-UID";`

## 2. Put it on GitHub Pages

1. On **github.com**, click **+ → New repository**. Name it `Money`, set it to **Public**, tick **Add a README**, and create it.
2. **Add file → Upload files**, drag in **everything inside this folder** (the files, not the folder), and click **Commit changes**.
3. **Settings → Pages**: Source **Deploy from a branch**, branch **main**, folder **/ (root)**, then **Save**.
4. After a minute or two it's live at **https://hollieduffield.github.io/Money/** (capital M, matching the repository name).

There's nothing to change in Firebase's authorised domains: `hollieduffield.github.io` is already there.

## 3. Install it

On your phone and iPad: open the address in **Safari → Share → Add to Home Screen**, open it from the new icon, and sign in with your My Planner email and password.

## Getting statements in

In your banking app or website, download your transactions as a **CSV** file, then in My Money tap **+ → Import statement**. The first time, check the columns in the preview; it remembers them for that bank after that. Re-importing overlapping dates is safe, because duplicates are skipped.
