# Bulk passport size maker

A tool for turning a folder of photos into passport-size photos in one go. We built it for a school that had photographed all its students and needed every photo at 150 × 200 pixels.

It is a single web page that runs in your browser. There is nothing to install, and the photos never leave your computer.

## How to get it

1. On this page, click the green **Code** button and choose **Download ZIP**.
2. Unzip the download.
3. Double-click `Passport Photo Maker.html`. It opens in Chrome or Edge.

Keep `passport-offline.js` in the same folder as the HTML file. It holds the face finder, the background remover and the iPhone photo converter. With it, the tool works without internet. Without it, those three features need a connection the first time you use them.

## How to use it

1. Click "Choose a folder" and pick the folder of photos, or drag the folder onto the page. Subfolders are included.
2. Pick a size. The default is 150 × 200 px. You can also type your own width and height in pixels, mm, cm or inches.
3. Look through the previews. Click a photo to fix it on its own.
4. Click "Save into a folder" or "Download as a ZIP file".

The resized photos go into a new folder named after the size, for example `passport_150x200`. The original photos are not changed.

## What it can do

Sizes

- 150 × 200 px, 35 × 45 mm, 2 × 2 inch, 50 × 70 mm, 33 × 48 mm, 1 × 1 inch, or any custom size
- Several sizes in one run, each saved to its own folder
- A maximum file size in KB for JPG files

Framing

- Finds each face, centres it and makes the head the same size in every photo
- Straightens tilted heads
- Marks photos that need checking: no face, more than one face, head cut off, face very small, blurry or dark

Background

- Replaces the background with white, red, light blue or any other colour
- Restore and Erase brushes for photos where the automatic cut-out is wrong

Lighting

- Brightness and contrast for the whole batch or for one photo

Names

- Reads a class list from Excel or CSV, or rows pasted from Excel
- Names the saved files by ID number or by student name

Printing

- Photo sheets on A4 to cut out
- A class sheet with every student's photo and name
- ID cards with the school name, crest and colour

To get a PDF, press Print and choose "Save as PDF" as the printer.

## The class list

Use four columns in this order: photo file name, ID number, student name, class. A header row is optional.

| Photo    | ID         | Name         | Class |
|----------|------------|--------------|-------|
| IMG_0012 | 0123456789 | Ama Mensah   | 2A    |
| IMG_0013 | 0123456790 | Kofi Boateng | 2A    |

If the list has only one column, the names are given to the photos in order.

## Known limits

- Use Chrome or Edge. "Save into a folder" is not available in Firefox or Safari; use the ZIP download there.
- iPhone HEIC photos are supported through a converter, but this has not been tested on real files yet.
- The background remover is less exact than paid services on loose hair and on backgrounds close to the student's skin or uniform colour. Check the previews before saving.
- The blurry and dark warnings are rough. Expect a few false alarms and a few misses.

## Credits

Face detection and background removal use Google's [MediaPipe](https://developers.google.com/mediapipe) models. HEIC conversion uses [heic2any](https://github.com/alexcorvi/heic2any). Both are bundled in `passport-offline.js`.

## Licence

See [LICENSE](LICENSE).
