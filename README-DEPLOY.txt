AiVic website deployment files
================================

WHAT'S IN THIS FOLDER
----------------------
index.html                     The full website. Self-contained (all styling,
                                scripts, and the logo are built into this one
                                file). This is the only file that needs editing
                                if the page content ever changes.
favicon.ico                    Browser tab icon (legacy/general).
favicon-16x16.png               "
favicon-32x32.png                "
apple-touch-icon.png           Icon used when someone saves the site to an
                                iPhone/iPad home screen.
android-chrome-192x192.png     Icon used on Android home screens / PWA.
android-chrome-512x512.png      "
site.webmanifest               Small config file that tells phones which
                                icon to use and what the site is called.

HOW TO DEPLOY ON SPACESHIP HOSTING
------------------------------------
1. Log in to Spaceship, go to the hosting file manager (or use FTP/SFTP)
   for the aivic.ca hosting plan.
2. Upload every file in this folder to the WEB ROOT (the top-level
   "public_html" or "www" folder, whichever Spaceship uses). Do not put
   them inside a subfolder, index.html needs to sit directly at the root
   so aivic.ca loads it automatically.
3. Confirm aivic.ca (and www.aivic.ca, if that's set up) points to this
   hosting plan via the domain's DNS/nameserver settings in Spaceship.
4. Visit aivic.ca in a browser to confirm it loads, and check the browser
   tab to confirm the AiVic icon shows up (may take a moment to update if
   the browser caches the old blank favicon).

BEFORE GOING LIVE, DOUBLE-CHECK
----------------------------------
Open index.html and find the <script> block near the very bottom of the
file. Two values need to be real before launch:

    const BOOKING_URL = "https://cal.com/your-aivic-link";
    const CONTACT_EMAIL = "hello@aivic.ca";

Replace BOOKING_URL with the real Cal.com/Calendly booking link, and
CONTACT_EMAIL with the real inbox that should receive "Send us a question
first" emails. Every "Book now" / "Book your AI Assessment" button and the
contact email link on the page pull directly from these two values, so
this is the only edit needed to make the whole site fully live.

That's it. No build step, no dependencies, no server-side code. It's a
static site, so any standard web hosting (including Spaceship's shared
hosting) can serve it as-is.
