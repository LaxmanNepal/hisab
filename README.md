# HISAB — Journal Voucher Dashboard

A lightweight, read-only web dashboard for browsing the worksheets in `Hisab.xlsx`.

## Live dashboard

After GitHub Pages is enabled, the dashboard will be available at:

https://laxmannepal.github.io/hisab/

## Features

- Header navigation for Calendar, Images and Receipt galleries
- Calendar shows each matching worksheet name on its date; click a sheet name to open it
- Original worksheet view preserves Excel cell structure and merged ranges
- Read-only accounting checks for debit/credit balance, possible duplicate voucher references and incomplete fields
- Responsive image gallery automatically reads files from `/images` and groups them by date
- Responsive receipt gallery reads multiple receipt photos per day from `/receipts`
- Automatically reads every worksheet in the workbook
- Switch between date-wise worksheets
- Search across all visible columns
- Sort any column by clicking its heading
- Choose how many rows to display
- Shows debit and credit totals when matching amount columns are detected
- Responsive layout for desktop, tablet and mobile
- No backend, database or sign-in required

## How the data is loaded

The page reads `Hisab.xlsx` directly from this repository using the SheetJS browser library. To publish each day's updated hisab, manually replace `Hisab.xlsx` in the repository while keeping the same filename. The dashboard always reads the latest committed workbook. Keep a local backup before replacing it. Refresh the dashboard after GitHub Pages publishes the change.

### Add supporting images

- Upload supporting images to `/images`.
- Upload receipt photos/scans to `/receipts`.
- Multiple receipt images for one date are supported.
- Put the date first in each filename, such as `2026-10-30-voucher-01.jpg` or `2026-10-30-receipt-02.png`.
- Supported formats: JPG, JPEG, PNG, WEBP, GIF and AVIF.
- Galleries are grouped by date automatically. New files appear after the site is refreshed.

## Enable GitHub Pages

1. Open **Settings → Pages** in this repository.
2. Under **Build and deployment**, choose **Deploy from a branch**.
3. Select branch **main** and folder **/(root)**.
4. Save and wait for GitHub Pages to publish the site.

## Important data and privacy notice

This repository is public. Anyone can view, copy or download the original Excel workbook, even if the dashboard itself has no download button. Do not publish personal information, customer details, account numbers, confidential company records or financial data unless you have permission and have properly anonymized it.

## Accuracy note

The dashboard displays worksheet data as found in the workbook. Debit and credit totals are best-effort summaries based on recognizable column headings; they are not an accounting reconciliation or audit. Always verify figures against the source workbook.

## Technology

- HTML, CSS and vanilla JavaScript
- [SheetJS](https://sheetjs.com/) for reading Excel in the browser
- GitHub Pages for static hosting
