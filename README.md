# Priyanka & Karan + Trupti & Dipak
## Royal Gujarati Heritage · Double-Wedding Digital Invitation

This is a complete static website, ready for GitHub Pages. Both couples have equal visibility and the design includes a ceremonial opening, six events, a live IST countdown, optimized Trupti & Dipak photographs, tasteful Priyanka & Karan placeholders, two galleries, a working Google Maps link, and a **static QR code** for the wedding venue. No database, paid hosting, or RSVP system is used.

### What is confirmed
- **21 November 2026, Saturday — Pre-wedding:** Mandap Muhurat at **8:30 AM**, Mameru at **10:00 AM**, Haldi at **2:00 PM**, Sangeet at **7:00 PM**.
- **22 November 2026, Sunday — Wedding:** Baraat Arrival at **7:00 AM** and Hast Melap at **11:45 AM**.
- **Countdown:** 22 November 2026, 11:45 AM India Standard Time, corresponding to `2026-11-22T06:15:00Z`.
- **Wedding venue:** Vataliya Prajapati ni Vadi, 1926, Vadva, Bhavnagar, Gujarat 364001, India.
- **Unconfirmed:** The **21 November pre-wedding venue**. No directions are shown for Day 1 until confirmed.

### Website folder
```
royal-gujarati-double-wedding/
  index.html
  assets/
    styles.css
    script.js
    heritage-arch.svg
    ornaments.svg
    favicon.svg
    wedding-venue-qr.png
  README.md
  QA-REPORT.md
  HTML-source-backup.txt
  single-file-invitation.html
  single-file-source-backup.txt
```

The main deployable website is `index.html` plus the entire `assets/` folder. The single-file version is optional; it contains CSS, JavaScript, vector decorations, and the venue QR embedded directly within one HTML document.

### GitHub Pages deployment (your existing repository)
Your existing repository is `remotedesktopdipak-droid/dipak-trupti-wedding`. This new website **replaces the current invitation design** if you deploy it in the root of that repository.

1. Visit https://github.com/remotedesktopdipak-droid/dipak-trupti-wedding .
2. Make a backup of the current `index.html` and any existing assets if you want to preserve the older website.
3. Upload the **new `index.html` and the complete new `assets/` folder to the repository root**. Replace files with matching names. Do not upload the outer `royal-gujarati-double-wedding` folder as an extra nested directory.
4. Commit the changes to the repository's publishing branch (usually `main`).
5. In **Settings → Pages**, set **Deploy from a branch**, choose your publishing branch, and select `/(root)` if not already configured.
6. Open https://remotedesktopdipak-droid.github.io/dipak-trupti-wedding/ and verify the opening, mobile display, venue link and QR on your own device.

**Alternative (one-file publishing):** Copy the contents of `single-file-invitation.html` into the repository-root `index.html`. This works without the other assets while photographs are placeholders. Once actual photos are added, the photo paths you configure must point to uploaded images.

### Replacing photographs later
Photographs for **Trupti & Dipak** have now been added and optimized. **Priyanka & Karan** and the optional sisters’ photograph still use intentional placeholders, without broken images. There are **11 slots**: two main portraits, four gallery photos for each couple, and one optional sisters' photo.

1. Optimize each photograph as `.webp` (sRGB recommended); aim for roughly 1200–1600 pixels on the long side for main portraits and 900–1200 pixels for gallery pictures. Preserve the original facial features and image content.
2. Place the pictures into `assets/` with these names:
   - `priyanka-karan-main.webp`, `trupti-dipak-main.webp`
   - `priyanka-karan-01.webp`, `priyanka-karan-02.webp`, `priyanka-karan-03.webp`, `priyanka-karan-04.webp`
   - `trupti-dipak-01.webp`, `trupti-dipak-02.webp`, `trupti-dipak-03.webp`, `trupti-dipak-04.webp`
   - `sisters-together.webp` (optional)
3. Open **`assets/script.js`** and find `PHOTO_CONFIG` at the top. For each picture you added, replace the matching `null` value with the path string. Example:
   ```js
   'priyanka-karan-main': 'assets/priyanka-karan-main.webp',
   'priyanka-karan-01': 'assets/priyanka-karan-01.webp',
   ```
   Leave other entries `null` until the corresponding photos arrive. Keep the quotes and commas.
4. Commit the images and edited script to the same GitHub repository. The gallery lightbox automatically becomes clickable for configured images that load successfully.
5. If using **the single-file version**, edit its embedded `PHOTO_CONFIG` instead of `assets/script.js`.

Never put a large raw photo into the HTML code or use an unoptimized 10MB background photo.

### Venue QR and Maps
The QR graphic is at `assets/wedding-venue-qr.png` and can also be downloaded separately. It contains the supplied Google Maps URL **directly**, without redirect or expiration service. A copy can be printed on physical cards. QR is static, but the external destination remains dependent on Google Maps and the place link staying valid.

For directions, the website opens Google Maps in a new tab. The address and place link were supplied for this invitation; physical venue details should still be confirmed with the family before sharing broadly.

### Technical notes
- Plain HTML/CSS/JavaScript; no build step and no server/backend needed.
- All local asset paths are relative, compatible with a GitHub Pages subdirectory.
- The only optional network-dependent enhancement is Google Fonts; readable serif/sans fallback fonts are configured.
- Web Share is supported on compatible browsers; otherwise the button copies the link.
- The site supports keyboard navigation, native accessible photo dialogs, lazy-loading of optional gallery photographs, and reduced-motion preferences.
- No RSVP form is included; background music is intentionally omitted.

### Testing
Read `QA-REPORT.md` for the tests carried out and the testing limitations.

### Updated photographs and event illustrations (30 October 2026)
- Trupti & Dipak main portrait: `trupti-dipak-main.webp`, a closer crop of the uploaded forest photograph (crop and compression only; faces unretouched).
- Trupti & Dipak gallery 01–04: all four uploaded photographs, in upload order.
- The images are compressed WebP files, resized without facial, skin or image retouching.
- Six local SVG event illustrations (`assets/event-*.svg`) show traditional motifs. These are illustrations, not photos of the actual ceremonies.
- Below-the-fold photos and event illustrations load lazily; the hero portrait starts loading eagerly.
- Replace `index.html` and the **whole** `assets/` folder when deploying.
