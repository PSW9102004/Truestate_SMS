# TruEstate Retail Sales Management System

## Overview
A comprehensive retail sales management dashboard built for TruEstate. This system parses sales data from a CSV, providing a high-performance backend API for searching, filtering, and sorting, coupled with a premium, pixel-perfect React frontend.

## Tech Stack
- **Backend**: Node.js, Express.js, CSV Parser
- **Frontend**: React, Vite, Vanilla CSS
- **Monorepo**: Managed via NPM scripts

## Implementation Summaries

### Search
Full-text, case-insensitive search implemented on the server-side, targeting:
- `Customer Name`
- `Phone Number`

### Filtering
Advanced filtering logic allows simultaneous multi-selection of:
- **Categorical**: Region, Gender, Category, Payment Method, Tags
- **Ranges**: Age (min/max), Date (start/end)

### Sorting
Supports sorting by:
- **Date** (Newest First)
- **Quantity**
- **Customer Name** (A-Z)

### Pagination
Server-side pagination defaults to **10 items per page**. The frontend automatically persists search and filter states while navigating through pages.

## Setup Instructions

1.  **Install Dependencies**
    ```bash
    npm run install:all
    ```
    *(This script automatically installs dependencies for both backend and frontend)*

2.  **Run Application**
    ```bash
    npm start
    ```
    - **Backend**: [http://localhost:5000](http://localhost:5000)
    - **Frontend**: [http://localhost:5173](http://localhost:5173)

---
###  Live Deployment
* **Live Application:** [https://truestate-sms.vercel.app/](https://truestate-sms.vercel.app/)
* **Backend API:** [https://truestate-sms.onrender.com/api](https://truestate-sms.onrender.com/api)
