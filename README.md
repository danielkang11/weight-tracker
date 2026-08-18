# Weight Tracker

A responsive, privacy-first weight tracking app built with vanilla HTML, CSS, and JavaScript. It records daily weights, visualizes trends, calculates summary statistics, and supports portable CSV and JSON backups without sending health data to a server.

## Highlights

- Track daily weights in kilograms or pounds
- Explore configurable date ranges of up to 366 days
- Visualize progress with a custom, dependency-free canvas chart
- Review minimum, maximum, average, delta, and overall trend
- Import and export CSV or JSON backups with validation and conflict handling
- Preserve entries locally in the browser with `localStorage`
- Use a responsive interface across desktop and mobile layouts

## Privacy

Weight entries remain in the browser's local storage. The repository contains no personal weight history, and the app does not send entered data to a backend.

Clearing browser storage will remove locally saved entries, so use the export tools to create backups when needed.

## Run locally

No build step or dependencies are required:

1. Clone or download this repository.
2. Open `index.html` in a modern browser.
3. Select **Load sample** to explore the interface without entering personal data.

## Technical approach

The app is intentionally framework-free. CSS provides the responsive glass-style interface, while a single JavaScript module handles date validation, unit conversion, persistence, import/export, statistics, and canvas rendering. Solid chart segments represent consecutive measurements; dashed segments indicate gaps in the data.

## Data formats

CSV imports require this header:

```csv
date,weight,unit
```

JSON imports use an array of records:

```json
[
  { "date": "08-01-2026", "weight": "75.2", "unit": "kg" }
]
```

Dates use `MM-DD-YYYY`, and supported units are `kg` and `lb`.
