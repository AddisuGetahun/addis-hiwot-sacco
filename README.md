# Addis Hiwot SACCO – Website + Admin Portal
አዲስ ህይወት የገንዘብ ቁጠባ እና ብድር ኀብረት ሥራ ማህበር

## Pages
- `/` landing page · `/register` public membership form · `/admin` staff portal (password login)

## How it works
1. A member fills `/register` (files are compressed in the browser and uploaded).
2. The application and files are stored with Netlify Blobs (no external database).
3. In `/admin` > **Applications**, staff open the ID/photo/signature, then **Approve** (creates the member, posts fee + shares to the cash book) or **Reject**.
4. Admin data (members, savings, loans, cash book) is saved on the server and loads on any device after login.

## Deploy (functions need a Git or CLI deploy, not drag-and-drop)
1. Push this folder to GitHub, then Netlify > Add new site > Import from Git. (Or: `npm i -g netlify-cli && netlify deploy --prod`.)
2. Site settings > Environment variables: `ADMIN_PASSWORD` (your password) and `ADMIN_SECRET` (any long random text).
3. Redeploy. Test locally with `npm i && npx netlify dev`.

## Limits
- Upload total about 4MB per application after image compression (Netlify function limit).
- One shared admin password; sessions last 8 hours. Roles in the admin portal are views, not separate logins.
- Back up your data: export features are not built yet.
