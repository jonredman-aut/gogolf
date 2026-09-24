# GoGolf setup (about 15 minutes, free)

Anyone with the link can join a round with a sign-up code. No Claude account needed.

## 1. Create the database (Firebase)
1. Go to https://console.firebase.google.com and sign in with a Google account.
2. Click **Create a project**, name it `gogolf`, and finish the prompts (Google Analytics is optional).
3. In the left menu, open **Build > Authentication**, click **Get started**, choose **Anonymous**, turn it on and save.
4. Open **Build > Firestore Database**, click **Create database**, pick a location near you (for example `us-central`), and start in **production mode**.
5. Still in Firestore, open the **Rules** tab, replace everything with the contents of `firestore.rules`, and click **Publish**.

## 2. Connect the app
1. In Firebase, click the gear icon > **Project settings**. Under **Your apps**, click the web icon `</>`, name it `gogolf`, and register it (skip hosting).
2. Copy the `firebaseConfig` values it shows.
3. Open `index.html` in any text editor, find `FIREBASE_CONFIG` near the top of the script, and paste your values in place of the placeholders. Save.

## 3. Put it online (Netlify)
1. Go to https://app.netlify.com/drop.
2. Drag the folder containing `index.html` onto the page. You get a link like `https://something.netlify.app`.
3. Optional: in Netlify's site settings, change the site name to something like `gogolf-yourname`.
4. Back in Firebase, go to **Authentication > Settings > Authorized domains** and add your Netlify domain.

## 4. Use it
- Send your group the link. On a phone, "Add to Home Screen" makes it open like an app.
- Add your course under **Courses**, then start a round under **Round** to get the sign-up code.
- Firebase's free Spark plan easily covers a regular foursome or a small league.

## Good to know
- Anyone who has both the link and a round's code can enter scores for that round, which is how a group scorecard works. Don't post the link publicly if that matters to you.
- Scores entered with weak signal on the course are saved on the phone and sync when signal returns.
- To update the app later, edit `index.html` and drag the folder onto Netlify again.
