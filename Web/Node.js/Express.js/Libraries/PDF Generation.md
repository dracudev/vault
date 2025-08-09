## Overview
Generating PDFs is a common requirement in web applications (e.g., invoices, reports, certificates). Two popular libraries in Node.js for this are:

- **Puppeteer:** Generates PDFs by rendering web pages in headless Chrome.
- **PDFKit:** Programmatically generates PDFs via a stream, drawing text, images, and shapes.

---

## Puppeteer

### Installation
```bash
npm install puppeteer
```

### Basic Example
```javascript
const puppeteer = require('puppeteer');

(async () => {
  const browser = await puppeteer.launch();
  const page = await browser.newPage();

  // Set HTML content or navigate to a URL
  await page.setContent('<h1>Hello PDF!</h1>');

  // Generate PDF
  await page.pdf({
    path: 'output.pdf',
    format: 'A4',
    printBackground: true
  });

  await browser.close();
})();
```

### Generating PDF from URL
```javascript
await page.goto('https://example.com', { waitUntil: 'networkidle0' });
await page.pdf({ path: 'webpage.pdf', format: 'A4' });
```

### Key Options for `page.pdf()`
| Option           | Description                     |
|------------------|---------------------------------|
| `path`           | File path to save PDF.          |
| `format`         | Paper format (e.g., A4, Letter). |
| `margin`         | Define margins (top, bottom, left, right). |
| `printBackground`| Include background graphics.    |

---

## PDFKit

### Installation
```bash
npm install pdfkit
```

### Basic Example
```javascript
const PDFDocument = require('pdfkit');
const fs = require('fs');

const doc = new PDFDocument();
doc.pipe(fs.createWriteStream('output.pdf'));

// Add text
 doc.fontSize(25).text('Hello PDFKit!', 100, 100);

// Add image
// doc.image('path/to/image.png', {
//   fit: [250, 300],
//   align: 'center',
//   valign: 'center'
// });

// Draw a rectangle
 doc.rect(100, 150, 100, 100).stroke();

doc.end();
```

### PDFKit Features
- **Text formatting**: Fonts, sizes, alignments.
- **Shapes and graphics**: Lines, rectangles, circles.
- **Images**: Embeds PNG and JPEG.
- **Links and annotations.**

### Streaming PDF to Client in Express
```javascript
const express = require('express');
const PDFDocument = require('pdfkit');

const app = express();

app.get('/generate-pdf', (req, res) => {
  const doc = new PDFDocument();
  res.setHeader('Content-Type', 'application/pdf');
  doc.pipe(res);

  doc.fontSize(25).text('Streaming PDF with PDFKit', 100, 100);

  doc.end();
});

app.listen(3000, () => console.log('Server running on port 3000'));
```

---

## Choosing Between Puppeteer and PDFKit
| Requirement                   | Use Library |
|-------------------------------|-------------|
| Rendering styled HTML/CSS     | Puppeteer   |
| Custom graphic drawing/text   | PDFKit      |
| Embedding complex layouts via HTML | Puppeteer |
| Programmatic generation with drawing API | PDFKit |

---

## Useful Resources
- [Puppeteer GitHub](https://github.com/puppeteer/puppeteer)
- [PDFKit Documentation](http://pdfkit.org/docs/)

---

## Summary
- **Puppeteer**: Ideal for converting HTML/CSS/webpages to PDF.
- **PDFKit**: Best for programmatically generated PDFs with custom graphics.

Both tools serve different use cases and can even complement each other in a complex application.
