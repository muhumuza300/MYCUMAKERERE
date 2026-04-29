==============================================
MYCU MAKERERE WEBSITE - DEPLOYMENT GUIDE
==============================================

WHAT YOU HAVE
-------------
A complete static website for Malaria Youth Champions Uganda
(Makerere Chapter), with the Kasanvu malaria portal as its
flagship project.

FOLDER STRUCTURE
----------------
mycu-website/
├── index.html          (Home page)
├── about.html          (About + executive team)
├── projects.html       (Projects grid - Kasanvu + future)
├── donate.html         (Pledge tracker + MTN/Airtel codes)
├── contact.html        (Contact form + partnerships)
├── shared.css          (Site-wide styles)
├── shared.js           (Mobile nav)
├── logo.jpg            (MYCU logo)
└── kasanvu/            (Kasanvu project sub-page)
    ├── index.html      (Full interactive dashboard)
    ├── data.js         (Real survey data)
    ├── logo.jpg
    └── images/
        ├── thumbs/     (30 photo thumbnails)
        └── full/       (30 full-size photos)

TEST IT LOCALLY FIRST
---------------------
1. Unzip mycu-website.zip
2. Double-click index.html
3. Click around all the pages, test the donate form,
   open the Kasanvu portal, click the map markers
4. Make sure everything works before deploying


==============================================
DEPLOY TO NETLIFY (5 minutes)
==============================================

EASIEST METHOD: DRAG AND DROP
------------------------------
This is the fastest way - no GitHub needed.

1. Go to https://app.netlify.com/
2. Log in (you said you already have an account)
3. On your Netlify dashboard, you'll see a box that says
   "Want to deploy a new site without connecting to Git?
    Drag and drop your site output folder here"
4. Drag the UNZIPPED 'mycu-website' folder into that box
5. Wait 30-60 seconds while Netlify uploads
6. You'll get a URL like: https://random-name-123.netlify.app
7. Click "Site settings" -> "Change site name"
   Choose something like: mycu-makerere
   Your URL becomes: https://mycu-makerere.netlify.app

DONE. Your site is live and public.


METHOD 2: VIA GITHUB (recommended for updates)
----------------------------------------------
Use this if you want auto-deploy when you change files.

A. Push to GitHub:
   1. Go to https://github.com/new
   2. Create a new repo named "mycu-website" (Public)
   3. DON'T initialize with README
   4. On the next page, GitHub shows you commands. You need:

      Open Terminal/Command Prompt in the unzipped folder:

      git init
      git add .
      git commit -m "Initial MYCU website"
      git branch -M main
      git remote add origin https://github.com/muhumuza300/mycu-website.git
      git push -u origin main

      (When prompted, use a GitHub Personal Access Token as your
       password - get one at github.com/settings/tokens)

B. Connect to Netlify:
   1. On Netlify dashboard, click "Add new site"
   2. Choose "Import an existing project"
   3. Click "Deploy with GitHub"
   4. Authorize Netlify to access your GitHub
   5. Select the "mycu-website" repo
   6. Build settings: leave everything as default
      (Build command: empty, Publish directory: empty or ".")
   7. Click "Deploy site"
   8. Wait 1 minute - your site is live

C. Future updates:
   Edit any HTML file -> push to GitHub -> Netlify auto-deploys


==============================================
AFTER DEPLOYMENT
==============================================

WHAT TO DO NEXT
---------------
1. Test the live site URL on your phone and computer
2. Click every link, every page, every button
3. Test the donate form - make sure it remembers pledges
4. Open the Kasanvu portal and click map markers
5. Share the URL on Twitter @MYCUMAK
6. Add the URL to your university recognition letter

CUSTOMIZE THE NETLIFY URL
-------------------------
Default: random-name-123.netlify.app
1. Netlify -> Site settings -> Site information -> Change site name
2. Choose: mycu-makerere or malariayouthmakerere
3. Save

THINGS YOU MIGHT WANT TO EDIT LATER
-----------------------------------
- about.html: Team avatar initials are auto-generated;
  if you want real photos, replace the .team-avatar divs with
  <img src="team/bbosa.jpg"> tags

- contact.html: Contact form uses mailto: which opens email client
  For a real form, sign up for free at formspree.io

- donate.html: Your real impact data ("Nets distributed",
  "Funds raised") will accumulate as people make pledges.
  These are stored in their browser localStorage.

PAYMENT TRACKING (IMPORTANT)
----------------------------
Mobile money payments to:
  MTN: 96622360
  Airtel: 7079806

These payments do NOT appear automatically on the website.
You'll need to:
- Check MTN/Airtel merchant dashboards weekly
- Manually update impact stats on home page
- Send thank-you receipts to donors who provide names

PLEDGE DATA
-----------
The pledge tracker stores data in each user's browser
(localStorage). To collect pledges centrally, you would
need to add a backend - something like Google Sheets +
Google Forms could work as a simple solution.


==============================================
TROUBLESHOOTING
==============================================

"My logo doesn't show up"
- Make sure logo.jpg is in the root folder AND in /kasanvu/

"The map doesn't load on the Kasanvu page"
- The map needs internet to load tiles from CartoDB
- It won't work fully offline

"Photos don't appear in the gallery"
- Make sure images/thumbs/ and images/full/ folders are
  uploaded with all 60 files

"My GitHub push fails"
- You need a Personal Access Token, not your GitHub password
- Get one at: github.com/settings/tokens (classic, with "repo" scope)


==============================================
QUESTIONS?
==============================================

You're set up to deploy this yourself. If you hit a wall,
the most common issue is GitHub authentication - use a
Personal Access Token, not your password.

The drag-and-drop method to Netlify is the simplest path
if you just want it live FAST.

Best of luck with the launch!

==============================================
