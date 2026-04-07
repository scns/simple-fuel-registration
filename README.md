# Simple Fuel Registration

Developed by [WP Plugin Factory](https://www.wppluginfactory.nl/)
[Plugin website](https://www.wppluginfactory.nl/simple-fuel-registration)

![Version](https://img.shields.io/badge/Version-1.6.2-blue)  ![WordPress](https://img.shields.io/badge/WordPress-6.0+-21759b)  ![PHP](https://img.shields.io/badge/PHP-8.0+-777bb4)  [![License](https://img.shields.io/badge/License-GPL--2.0--or--later-green)](https://www.gnu.org/licenses/gpl-2.0.html)

---

> Register fuel fill-ups effortlessly from a receipt photo. AI reads all relevant data automatically and saves it to your WordPress site.

## Description

Simple Fuel Registration makes tracking fuel fill-ups effortless. Take a photo of your receipt, upload it in the plugin, and GPT-4o Vision automatically reads all relevant details:

- Date and time of the fill-up
- Name and location of the fuel station
- Fuel type (Petrol, Diesel, LPG, etc.)
- Number of litres
- Price per litre
- Total amount
- Mileage (if printed on the receipt)

All data is stored in a clear overview table with statistics such as total litres filled, total amount spent, and average price per litre.

**Features:**

- Upload receipts via drag & drop or directly from the camera
- Automatic data extraction via OpenAI GPT-4o Vision
- Fuel types are automatically normalised (e.g. EURO 95 → Petrol)
- Image automatically resized and optimised on upload (max 1600 px, JPEG 82 %)
- Overview of all fill-ups with search, filter and pagination options
- Statistics: total litres, total cost, average price/litre
- Support for multiple vehicles
- **Quick capture link** — a secret URL you can bookmark on your phone to upload a receipt without logging in; the receipt is saved instantly and AI analysis runs in the background via a scheduled cron job *(Full licence only)*
- **Export / Import** — download all fuel entries as a ZIP (JSON + CSV + photos) and re-import them on any site
- **Statistics page** — monthly charts, price trend, fuel distribution, heatmap and top stations *(Full licence only)*
- **Lite licence** — manage 1 vehicle, add fill-ups and use AI analysis; locked features are shown greyed-out with a clear upgrade notice
- **Full licence / Trial** — all features unlocked: multiple vehicles, statistics, quick capture link
- Built-in debug mode for inspecting raw AI responses
- Separate licence page with status overview, manual validation, and trial request
- Automatic daily licence verification in the background
- Free 1-month trial available — activate directly from within the plugin

**Requirements:**

- An active licence or a free trial (request via Fuel Registration → Licence)
- An OpenAI API key with credit (platform.openai.com)

## Installation

1. Upload the `simple_fuel_registration` folder to `/wp-content/plugins/`, or install the plugin directly
   via the WordPress admin screen under Plugins → Add New Plugin → Upload Plugin.
2. Activate the plugin through the 'Plugins' menu in WordPress.
3. Go to **Fuel Registration → Licence**.
4. Enter your **email address** and **licence key** and click 'Activate Licence',
   or click 'Request Trial & Activate' for a free 1-month trial.
5. Go to **Fuel Registration → Settings** and enter your **OpenAI API key**
   (available at platform.openai.com/api-keys).
6. Optionally set a default vehicle.
7. Go to **Fuel Registration → Add New** to log your first fill-up.

## Frequently Asked Questions

### Which file formats are supported for receipts?

JPG, PNG and WEBP. Photos taken with a phone or tablet work great.

### How large can the photo be?

Up to 10 MB on upload. The plugin automatically resizes the image to a maximum of 1600 × 1600 px
and saves it as an optimised JPEG, keeping the stored file size much smaller.

### How much does AI analysis cost?

You pay OpenAI directly. GPT-4o Vision costs approximately $0.002 per image.
With $5 of credit you can analyse over 2,500 receipts.

### Does the plugin work without an OpenAI API key?

Yes. You can also enter fill-ups entirely manually. AI analysis is optional.

### How do I enable debug mode?

Go to Fuel Registration → Settings → AI Receipt Analysis and tick 'Show OpenAI response during receipt analysis'.
After analysis a panel appears showing the extracted field values, raw JSON, and technical details.

### How does the quick upload link work?

Go to Fuel Registration → Settings → Quick Receipt Upload. Generate a secret link and save it
as a home screen shortcut on your phone (iOS: Share → Add to Home Screen; Android: Menu → Add Shortcut).
Via the link you can upload a photo without logging in. The receipt is saved immediately and AI analysis
runs automatically in the background every few minutes. The processed entry appears at the top of the
dashboard overview, where you can review, edit and approve it.
Do not share the link with others — anyone with the URL can upload receipts.

### Are my receipts sent anywhere?

The image is sent exclusively to OpenAI for analysis. No data is stored or shared with any third party
outside of OpenAI. Please refer to OpenAI's privacy policy for more information.

### How do I activate my licence?

Go to Fuel Registration → Licence. Enter the email address and licence key you received when purchasing
and click 'Activate Licence'. Don't have a licence yet? Request a free trial on the same page.

### How often is the licence checked?

The licence is automatically verified every 24 hours in the background. You can also validate manually
at any time using the 'Validate Licence' button on the licence page.

### Can I request more than one trial?

No. Each website (domain) may request a trial only once. An ongoing paid licence is required for
unlimited use.

## Screenshots

1. Overview page with statistics and all fill-ups
2. Add fill-up — upload receipt and run AI analysis
3. Licence page with status overview, validation button and trial request
4. Settings page with OpenAI configuration and debug mode
5. Debug panel with raw AI response and extracted field values

## Changelog

### 1.6.2

- Added: E-mailnotificatie voor overige bonnen — eigen onderwerp, HTML-template en test-mailknop
- Added: 'Mailen'-knop per goedgekeurde overige bon in het overzicht
- Added: Downloadknop in overige bon-mail via beveiligde token-URL

### 1.6.1

- Fixed: Overige bonnen werden niet via de cron verwerkt als er geen tankbonnen in de wachtrij stonden

### 1.6.0

- Added: Module 'Overige bonnen' — upload en beheer van niet-brandstofbonnen gekoppeld aan een voertuig/kenteken
- Added: Categorieën voor overige bonnen — zelf te beheren lijst (vergelijkbaar met voertuigen)
- Added: AI-analyse van overige bonnen — extraheert leverancier, locatie, datum, bedrag en stelt categorie voor
- Added: Quick Capture-pagina uitgebreid met Tankbon/Overige bon-toggle, voertuigkeuze en categoriekeuze
- Added: Statistiekenpagina toont overige kosten: kaarten, maandgrafiek (gecombineerd), categorie-donut en totaaloverzicht
- Added: Kaart toont overige locaties als oranje markers naast blauwe tankstationmarkers
- Improved: Menuvolgorde en -namen verduidelijkt

### 1.5.0-beta.1

- Performance: Foto's worden nu client-side verkleind (max 1600px) vóór het uploaden — upload is ~10× sneller op mobiel
- Performance: Tussentijdse WordPress-thumbnailgeneratie overgeslagen bij bonuploads (niet nodig voor bonnetjes)
- Added: Plugin icoon en banner voor het WordPress-updatescherm
- Fixed: Compatibiliteit gemarkeerd als getest tot WordPress 6.9.4

### 1.0.1

- Fixed: License server API responses now consistently use `expires_at` key — expiry date was not stored locally after activation
- Fixed: `license_type` (Full/Lite/Trial) is now correctly saved during activation
- Fixed: License server now rejects activation requests with an empty domain

### 1.0.0

- Eerste stabiele release
- Added: Bonnen uploaden via publieke quick-capture pagina (mobiel-vriendelijk)
- Added: AI-analyse van bonnen — extraheert brandstoftype, liters, prijs per liter, totaalprijs, kilometerstand en tankstation automatisch
- Added: Duplicaatdetectie — AI-verwerkte bon wordt automatisch als dubbel gemarkeerd als er al een overeenkomend record bestaat
- Added: Overzichtspagina met filteropties, statussen (in wachtrij, in behandeling, goedgekeurd, afgekeurd, dubbel) en kaartweergave
- Added: Beheerder kan bons goedkeuren, afkeuren of als dubbel overschrijven
- Added: Statistieken-dashboard met grafieken en heatmap
- Added: Export/import functionaliteit
- Added: E-mailnotificaties bij nieuwe uploads
- Added: GitHub-gebaseerd automatisch updatesysteem
- Added: Beta-kanaal optie in instellingen
- Added: Licentiesysteem
- CI: GitHub Actions release pipeline met automatische ZIP-build en publicatie naar publieke update-repo

### 0.1.0 Beta 17

- CI: Release workflow gefixed — duplicate permissions/jobs blokken verwijderd, secrets-context in if-expressie vervangen door shell-check
- CI: Labels workflow toegevoegd met emoji-namen en automatische sync via gh CLI
- CI: Dependabot, PHP lint en release workflow permissions gecorrigeerd

### 0.1.0 Beta 16

- CI: GitHub Actions release workflow toegevoegd — bouwt ZIP, maakt release op private repo en publiceert naar publieke update-repo
- CI: Changelog wordt automatisch uitgelezen uit readme.txt bij elke tag-push

### 0.1.0 Beta 15

- Added: "Beta-versies ontvangen" optie op de Instellingen-pagina — als dit aanstaat haalt de updater ook GitHub pre-releases op; uitstaat = alleen stabiele releases
- Improved: Updater wist de release-cache automatisch zodra de beta/stabiel instelling wordt gewijzigd, zodat de volgende update-check het juiste kanaal gebruikt

### 0.1.0 Beta 14

- Added: GitHub-based automatic update system — WordPress now detects new releases from github.com/scns/simple-fuel-registration and offers one-click updates via Dashboard → Updates
- Added: Version number, plugin name and link to wppluginfactory.nl shown at the bottom of the public upload page
- Added: "Toch toevoegen" override button on duplicate receipt cards — allows approving a flagged duplicate when needed
- Added: Duplicate receipt cards now show a clear "⚠ Mogelijk dubbel" warning chip below the date
- Fixed: Plugin header version was stuck at beta.10; all three version locations (header, SFR_VERSION constant, readme) are now kept in sync

### 0.1.0 Beta 13

- Added: "Afkeuren" (Reject) button for pending receipt cards — rejects the bon and permanently deletes the uploaded receipt image from the media library in one click
- Confirmed: The existing Delete action also permanently deletes the associated attachment from the media library (wp_delete_attachment with force-delete), so no orphaned files remain
- Added: New admin notice "Bon afgekeurd en verwijderd (inclusief afbeelding)." shown after a rejection
- Added: .sfr-reject-btn CSS class — a solid red border button that turns fully red on hover to visually distinguish Reject from Delete

### 0.1.0 Beta 12

- Added: Automatic duplicate detection after background AI analysis — if the AI extracts enough data (date, total price and station name) and a matching approved/pending entry already exists, the receipt is saved with status 'duplicate' instead of 'pending'
- Added: Duplicate receipts appear in the pending overview with a red ⚠ DUBBEL chip and a red left border; only the Delete button is shown (no Approve or Edit)
- Added: get_duplicate() method added to SFR_Database to retrieve all entries with status 'duplicate'
- Improved: count_actionable() now also counts entries with status 'duplicate' so the admin menu badge reflects duplicates as well

### 0.1.0 Beta 11

- Fixed: Admin menu badge HTML embedded in the menu title corrupted WordPress hook names (e.g. fuel-registration-3_page_*), causing CSS, JS and charts to fail on all submenu pages when pending items were present; badge is now injected via the $menu / $submenu globals after registration
- Added: Pending receipt overview now shows fuel type, litres, price per litre, total price and mileage as small coloured chips for quick review without opening the entry
- Added: Station name and location are both shown on the pending receipt card
- Added: Inline vehicle quick-select dropdown on each pending receipt card — change the vehicle directly from the overview without opening the edit form; saved immediately via AJAX

### 0.1.0 Beta 10

- Fixed: Quick capture upload page now sends correct no-cache headers (nocache_headers, X-LiteSpeed-Cache-Control, DONOTCACHEPAGE) to prevent caching plugins and LiteSpeed from storing the page — a cached nonce would expire after 24 h and cause upload failures
- Fixed: Nonce verification failure on the quick capture upload now returns a clear error message instead of the generic WordPress -1 response
- Fixed: JPEG files with non-standard MIME type (image/jpg, image/pjpeg) are now accepted in all upload handlers and the AI analyser
- Fixed: Admin file input accept attribute updated to explicitly include .jpeg and .jpg extensions
- Fixed: Client-side file type check in admin.js now also accepts image/jpg and image/pjpeg, with a fallback extension check for browsers that report an empty file.type
- Added: Admin menu badge (red bubble) showing the number of receipts waiting for action (queued + pending) on the Fuel Registration menu item and the Overview submenu
- Added: count_queued() and count_actionable() methods added to SFR_Database

### 0.1.0 Beta 9

- Added: Mileage (odometer reading) input field on the quick capture upload page — users can now enter their current mileage before submitting a receipt
- Improved: Receipt upload on the quick capture page now returns immediately; the entry is saved with status 'queued' and AI analysis no longer blocks the upload request
- Added: Background cron job (SFR_Cron_Processor) that runs every 5 minutes and sends queued receipts through GPT-4o Vision, then promotes each entry to 'pending' for admin review
- Added: get_queued() method added to SFR_Database to retrieve all entries with status 'queued'
- Added: Configurable cron interval via the sfr_cron_interval option (value in minutes, default 5)
- Improved: User-supplied mileage is preserved; the AI-parsed mileage is only used when no mileage was entered manually
- Improved: Cron schedule is automatically cleared when the plugin is deactivated

### 0.1.0 Beta 8

- Fixed: Receipt thumbnail in the overview was broken when the image was renamed during resize (e.g. .jpeg → .jpg); the URL is now re-fetched after resize
- Fixed: Dashboard thumbnail now uses receipt_attach_id as a fallback when the stored URL no longer matches the actual filename
- Improved: Randomised filenames are now also applied to Quick Capture uploads

### 0.1.0 Beta 7

- Fixed: PHP syntax error in class-sfr-admin.php (line 713) caused by missing thumbnail initialisation
- Added: 'Sender name' and 'Sender address (From)' setting under Settings → Mail Receipt
- Improved: Mail sending now uses three independent HTML content-type mechanisms (header, wp_mail_content_type filter and phpmailer_init hook) for maximum compatibility with SMTP plugins
- Improved: Recipients are passed as a comma-separated list for broader SMTP compatibility
- Improved: The From header is only set when the configured sender address is a valid email address

### 0.1.0 Beta 6

- Added: Statistics page (Fuel Registration → Statistics) with date range, vehicle and fuel type filters
- Added: Monthly overview chart (costs as bar, litres as line — dual y-axis)
- Added: Price per litre over time (line chart, one series per fuel type)
- Added: Fuel distribution doughnut chart (Chart.js 4)
- Added: Top-15 stations table filtered by the selected period / vehicle
- Added: Interactive map (Leaflet.js + OpenStreetMap) with heatmap of all refuelling locations
- Added: On-demand geocoding of fuel stations via Nominatim/OSM (cached 30 days, 1 req/s)
- Added: Summary of 6–8 aggregated statistics (fill-ups, litres, costs, average price/L, etc.)
- Added: Licence tier system — Lite vs Full licence
- Added: Full/Trial licence unlocks all features; Lite licence is limited to 1 vehicle, no statistics, no quick capture link
- Added: Locked features are visible but disabled with a grey overlay and an upsell badge ("Upgrade to Full")
- Added: Lite notice at the top of pages with restricted features (blue info block with link to the licence page)
- Fixed: Geocoding failed for combinations of station name + address — now uses a two-step fallback (full address → address only)
- Fixed: Failed geocoding attempts were cached as null for 7 days, causing the retry link to disappear — null cache reduced to 1 day and locations are always shown in the queue
- Fixed: Charts were not rendered because the inline script ran before Chart.js had loaded

### 0.1.0 Beta 5

- Added: Export / Import page (Fuel Registration → Export / Import)
- Added: Export all fill-ups as a ZIP archive containing export.json (re-importable), export.csv (Excel) and optionally all receipt images
- Added: Import a previously created export ZIP including receipt images
- Added: Import options: skip duplicates (date + station + total) and import as 'pending review'

### 0.1.0 Beta 4

- Added: Quick upload link — secret URL for uploading receipts without logging in (Settings → Quick Receipt Upload)
- Added: Receipts uploaded via the quick link are saved as 'pending review'
- Added: Dashboard shows pending receipts at the top with options to edit, approve or delete them
- Added: Dashboard overview only shows approved fill-ups (pending entries are shown separately)
- Added: 'Generate new link' button to refresh the upload URL (the old link is immediately invalidated)
- Fixed: Database table updated with status column (default 'approved' — existing entries are not affected)

### 0.1.0 Beta 3

- Fixed: UTF-8 BOM removed from PHP files (caused JSON parse errors in AJAX calls)
- Fixed: Column raw_ai_response added to the database table via dbDelta
- Fixed: 'Save failed' error message is now displayed correctly when the database insert fails
- Fixed: Manually adding a fill-up now works correctly

### 0.1.0 Beta 2

- Added: Licence settings moved to a dedicated 'Licence' menu item
- Added: Ability to request a free 1-month trial and activate it directly
- Added: Trial is automatically linked to the current domain and activated upon request
- Added: Manual validation button on the licence page to check the licence immediately
- Added: 'Last verified' timestamp visible on the licence page
- Added: Badge colours for licence types Lite and Full
- Added: Author changed to WP Plugin Factory
- Fixed: Settings page now only shows AI and debug options (licence block removed)
- Fixed: Redirect after activation/deactivation now correctly points to the licence page
- Added: Fill-up time is read from the receipt and stored (HH:MM format, 24-hour clock)
- Added: Automatic duplicate receipt check during AI analysis based on date, station and total price

### 0.1.0 Beta 1

- Added: First public beta release
- Added: Upload receipts via drag & drop or directly from the camera
- Added: Automatic data extraction via OpenAI GPT-4o Vision
- Added: Fuel types are automatically normalised (e.g. EURO 95 → Petrol, gasoil → Diesel)
- Added: Image automatically resized and optimised on upload (max 1600 px, JPEG 82 %)
- Added: Overview of fill-ups with search, filter and pagination
- Added: Statistics: total litres, total cost, average price/litre
- Added: Support for multiple vehicles
- Added: Debug mode for inspecting raw AI responses
- Added: Licence activation via the licence server
- Added: Automatic daily licence verification in the background

## Upgrade Notice

### 0.1.0 Beta 10

Fixes upload failures caused by cached nonces on LiteSpeed and other caching servers. JPEG files are now correctly accepted. Admin menu now shows a badge count for receipts awaiting processing.
