# Charlotte Wood Carvers Showcase Application - Documentation

## Project Overview
This directory contains the source documentation for the **Charlotte Wood Carvers Showcase Application**. The application is used to manage the wood carver competition on the day of the event, including competitor check-in, judging, payment processing, and user management.

The documentation is written in **Markdown** and is structured to be hosted on **GitHub Pages**, providing an accessible, mobile-friendly guide for event volunteers and administrators.

## Directory Structure
The project consists of a single `docs/` directory containing all documentation files.

```
./
└── docs/
    ├── index.md                  # Main landing page and navigation hub
    ├── Check-In.md               # Competitor check-in workflow
    ├── Judging.md                # Judging team workflow
    ├── Setup-Judging.md          # Judging configuration workflow
    ├── Payment-Processing.md     # Finance team workflow
    ├── User-Management.md        # Administrator guide for managing users
    ├── General-Application-Usage.md # (Renamed to index.md)
    ├── Categories.md             # (Placeholder) Competition category config
    ├── Prizes.md                 # (Placeholder) Prize config
    └── Vendors.md                # (Placeholder) Vendor management
```

## Key Files & Modules

### Core Documentation
*   **`docs/index.md`**: The entry point for the documentation site. It covers general application usage (navigation, common icons, standard behavior) and links to specific modules.
*   **`docs/Check-In.md`**: Instructions for volunteers checking in competitors. Covers searching for carvers, confirming entries, and handling payments.
*   **`docs/Judging.md`**: Instructions for judging teams. Covers filtering by team, scoring entries (1st, 2nd, 3rd), and using numeric inputs.
*   **`docs/Setup-Judging.md`**: Instructions for Admins and Judging Managers to configure judging categories and assign teams.
*   **`docs/Payment-Processing.md`**: Instructions for the Finance Team. Covers fee calculations (including overage fees), payment methods (Cash/Check/Online), and receipt handling.
*   **`docs/User-Management.md`**: Instructions for Administrators. Covers adding users, Google Account requirements, and AppSheet sharing permissions.

### Future/Placeholder Modules
*   **`docs/Categories.md`**, **`docs/Prizes.md`**, **`docs/Vendors.md`**: Placeholder files for Event Configuration modules that are currently under development.

## Usage
1.  **Editing**: Modify the Markdown files in the `docs/` directory to update instructions.
2.  **Publishing**: The documentation is designed to be served via **GitHub Pages** from the `/docs` folder on the `master` branch.
3.  **Access**: Volunteers access the live site via their mobile devices, tablets, or laptops during the event.

## Conventions
*   **Navigation**: All pages should link back to the main menu or follow the "Main Menu > Module > Submenu" pattern.
*   **UI Descriptions**: Use bold text for UI elements (e.g., **Save**, **Cancel**).
*   **Screenshots**: Use placeholder text `![Screenshot: Description](path/to/image.png)` for images until actual screenshots are available.
*   **Behavior Notes**: explicitly mention that **Save** and **Cancel** actions do not typically show confirmation messages.
