Ristorante Rossini - Category/Admin Fix

Upload this whole folder to Netlify (or drag the ZIP contents into Netlify).

Admin URL:
https://YOUR-SITE.netlify.app/admin/

IMPORTANT:
- The admin manager is hidden until Firebase Authentication login succeeds.
- This version forces a fresh Firebase login whenever /admin/ is opened.
- After login you can add/delete categories and add/edit/delete food items.
- Existing categories: Pasta, Pizza, Dolci.
- New categories are stored in Firestore collection: categories.
- Menu items are stored in Firestore collection: menu.
- Image field currently uses an image URL. Firebase Storage uploads require Storage to be enabled on the project.


IMPORTANT FIX v2:
Categories are now stored as special documents inside the existing 'menu' collection, so no separate Firestore 'categories' collection/rules are required. This fixes the 'Loading categories...' issue when only menu collection permissions are configured. New custom categories also appear on the public menu automatically.
