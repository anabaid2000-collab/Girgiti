# Ristorante Rossini

GitHub Pages-ready restaurant menu with a Firebase-powered admin panel.

## GitHub Pages

In your GitHub repository:

1. Open **Settings → Pages**.
2. Under **Build and deployment**, choose **Deploy from a branch**.
3. Select branch **main** and folder **/(root)**.
4. Save and wait for the deployment to finish.

For a repository named `REPOSITORY`, the public URL is:

`https://USERNAME.github.io/REPOSITORY/`

Admin panel:

`https://USERNAME.github.io/REPOSITORY/admin/`

The navigation links in this version use relative paths, so they work correctly on GitHub Pages project sites.

## Firebase Authentication

The admin panel uses Firebase Authentication. In Firebase Console:

**Authentication → Settings → Authorized domains**

Add your GitHub Pages host, for example:

`USERNAME.github.io`

Make sure the admin email/password account exists under **Authentication → Users**.

If login shows `auth/unauthorized-domain`, the GitHub Pages domain has not been added to Firebase's Authorized domains.

## Firestore

The menu is stored in the `menu` collection. Category documents have:

- `type: "category"`
- `name: "Category Name"`

Menu items are normal documents in the same collection.

The supplied `firestore.rules` allows public reads and authenticated writes. For a real production site, restrict writes to the specific admin account rather than every authenticated Firebase user.

## Important

Do not publish Firebase service-account/private keys in this repository. The Firebase web configuration in the HTML is normally a client-side configuration, but Firestore Security Rules and Authentication must still be configured correctly.
