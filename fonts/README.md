# Quipd — Fonts

## Included (woff2, for web companion)

These woff2 files are for the GitHub Pages web companion at quipd.app.

- **DM Sans** — 400 (regular), 500 (medium)
- **Caveat** — 400 (regular)
- **JetBrains Mono** — 400 (regular), 500 (medium)

## For Xcode / iOS (TTF required)

Xcode requires TTF or OTF files. Download from Google Fonts:

1. **DM Sans**: https://fonts.google.com/specimen/DM+Sans
   - Download, extract, add `DMSans-Regular.ttf` and `DMSans-Medium.ttf` to Xcode target

2. **Caveat**: https://fonts.google.com/specimen/Caveat
   - Download, extract, add `Caveat-Regular.ttf` to Xcode target

3. **JetBrains Mono**: https://fonts.google.com/specimen/JetBrains+Mono
   - Download, extract, add `JetBrainsMono-Regular.ttf` and `JetBrainsMono-Medium.ttf` to Xcode target

After adding to Xcode:
- Check "Target Membership" for each font file
- Add font filenames to Info.plist under "Fonts provided by application" (UIAppFonts)

## Licence

All three fonts are licensed under the SIL Open Font License 1.1 (OFL).
Free for personal and commercial use.
