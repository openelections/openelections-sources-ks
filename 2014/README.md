2014 pdftotext and OCR
--------------------------------------

The Shawnee county PDF was created by scanning the original paper printout.
Therefore we couldn't simply run `pdftotext` on it since it is primarily an image.

Instead, we opened it using OS X Preview app, and selected *File -> Export...* and saved
it as a `.tiff` file at 300 pixels/inch.

Then, we used the `tesseract` OCR tool to convert it to text:

```bash
% tesseract -l eng 2014-General-Election-Shawnee-County---Precinct-Level-SOVC.tiff 2014-General-Election-Shawnee-County---Precinct-Level-SOVC
```

For the other PDF files that were created natively (not scanned), we used the `pdftotext` tool:

```bash
% pdftotext -table 2014-General---Sedwick-County---Precinct-Level.pdf
% pdftotext -table 2014-General---Wyandotte-County---Precinct-Level.pdf
% pdftotext -table 2014-General---Johnson-County---Precinct-Level.pdf
```

The `pdftotext` and `tesseract` tools were both installed on OS X using Homebrew.
