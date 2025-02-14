# PNM CSV Checker

A web-based tool that compares data from **three CSV files**—PNM Project Tracker, Trello Staking Tracker, and SPIDAmin Tracker—and displays matching or missing data for GIG-based projects. It also allows filtering by project name, status, and assigned email, and provides several CSV export options.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Setup & Usage](#setup--usage)
- [Adding or Updating User Emails and Assigned Names](#adding-or-updating-user-emails-and-assigned-names)
- [Code Breakdown (Non-Programmers)](#code-breakdown-non-programmers)
- [Common Questions](#common-questions)

---

## Overview

**PNM CSV Checker** lets you quickly see discrepancies between three CSVs:

1. **PNM Project Tracker**  
2. **Trello Staking Tracker**  
3. **SPIDAmin Tracker**

It filters projects that start with `"GIG"`, offers flexible search and filter options, and exports multiple CSV reports (detailed, simple, “Whatsup,” and a filtered subset).

---

## Features

- **Drag & Drop** or click‐to‐select for each CSV (PNM, Trello, SPIDAmin).
- **Filter** GIG-based projects by:
  - Name (contains your typed search).
  - Status (from SPIDAmin).
  - Assigned (from SPIDAmin emails).
- **Exports**:
  - **Comparison CSV**: Detailed row-by-row comparison.
  - **Simple CSV**: Summarized rows for each tracker.
  - **Whatsup CSV**: Summarized “what’s missing?” status.
  - **Filtered CSV**: The currently displayed data (columns: Project Name, SPIDAmin Status, PNM Status, Trello Status).

---

## Setup & Usage

1. **Clone or Download** this repository.
2. Place your **logo** file (e.g. `logo.png`) in the **same folder** as `index.html`.  
   - If you have your logo elsewhere or named differently, update the `<img src="logo.png">` in the HTML.
3. **Open `index.html`** in a web browser.
4. **Load the CSVs** by:
   - Dragging and dropping each CSV onto the corresponding drop zone, **or**
   - Clicking each drop zone and selecting the CSV file from your computer.
5. **Click "Compare Trackers"** once all three are loaded.
6. **Filter** the displayed results if desired:
   - Search by project name (only GIG-based projects are shown).
   - Filter by SPIDAmin status (drop-down).
   - Filter by SPIDAmin assigned email (drop-down).
7. **Export** using the available buttons:
   - **Download Comparison CSV**
   - **Download Simple CSV**
   - **Export Whatsup**
   - **Download Filtered CSV** (only appears if some filtered GIG projects are displayed)

---

## Adding or Updating User Emails and Assigned Names

### SPIDAmin "Assigned" Emails

In the code (near the top of the `<script>`), you’ll find:

```js
const spidaminEmailList = new Set([
  "landon.rodgers@txnmenergy.com",
  "hunter.mooney@txnmenergy.com",
  "wesley.simpson@txnmenergy.com",
  "tom.devuyst@pnmresources.com",
  "ryan.miller@txnmenergy.com"
]);
