# Architecture Documentation

## Project Structure (Monorepo)
The project follows a strict separation of concerns between the Backend (Logic/Data) and Frontend (Presentation).

```
root/
├── backend/    # Node.js/Express API
└── frontend/   # React Single Page Application
```

## Backend Architecture
- **Layered Approach**:
    - **Routes**: Define API endpoints (`/api/sales`).
    - **Controllers**: Handle HTTP requests, input validation, and coordinate services.
    - **Services**: Business logic. `DataService` handles CSV parsing and in-memory data processing (Search/Filter/Sort).
    - **Models**: JS Objects/Classes representing the Data Schema.

- **Data Flow**:
    1.  Server Start -> `DataService` loads CSV into memory.
    2.  request -> `SalesController` extracts query params.
    3.  `SalesController` calls `DataService.query(params)`.
    4.  `DataService` applies filters -> search -> sort -> pagination.
    5.  Response -> `SalesController` sends JSON.

## Frontend Architecture
- **Component-Based**:
    - `SalesTable`: Displays data in a responsive grid.
    - `FilterPanel`: Contains all filter inputs.
    - `SearchBar`: Global search input.
- **State Management**:
    - `useSales` Hook: Centralizes API calls and state (loading, error, data, current filters).
- **Styling**:
    - Vanilla CSS (scoped via CSS Modules or standard imports) to ensure specific design adherence without framework override issues.

## Data Ingestion
The system ingests `truestate_assignment_dataset.csv`.
- **Parsing**: Done at startup using stream-based parser to handle large files efficiently.
- **Storage**: In-Memory (Array of Objects) for this assignment to ensure maximum speed for filtering/sorting.
