I need you to act as a **product manager** and write a detailed **Product Requirements Document (PRD)** and **user stories** for a web application that will be built in Python using the **FastHTML** framework. The app will allow users to upload a CSV file containing addresses, geocode those addresses using Google Maps API, display the geocoded locations on an interactive map, and include a thematic legend with user-selectable features. Each flow of data (file upload, geocoding, etc.) will be saved as a **workspace** in the database, allowing users to save and manage multiple projects separately.

### 1. **User Flow:**
- The user uploads a CSV file containing a list of addresses.
- The application geocodes the addresses using the Google Maps API.
- The geocoded points are plotted on a map.
- A sidebar displays a **legend** showing thematic mapping of the points, based on a column called "sector" (which is generated automatically when the file is uploaded).
- The legend should:
  - Show the **colors** representing different sectors on the map.
  - Allow users to **select a different numeric column** from the file, to aggregate data (sum and count) per sector.
  - Display the **number of points** in each sector.
- The user can select points on the map. When points are selected:
  - The values in the legend should update temporarily to show the impact of the selected points (such as changing the aggregated values).
  - The changes can be persisted if the user opts to **save** the changes.
- The user can create, manage, and switch between **workspaces**, each representing a separate flow (CSV file upload, geocoding, map visualization).
- Each workspace is stored in the **database**, allowing users to save their progress and continue working later.

### 2. **Technical Requirements:**
- **Frontend**:
  - Built using **FastHTML** framework.
  - Map rendering should use a suitable library such as **Leaflet.js** or **Google Maps API**.
  - Sidebar with interactive **legend** showing color-coded sectors, the option to select other numeric columns, aggregation features (sum and count), and real-time updates when points are selected.
  - Selection of map points should dynamically update the sidebar data.
  - A **workspace management UI** that allows users to create, delete, or switch between saved workspaces.
- **Backend**:
  - **Python FastAPI** to handle file uploads, geocoding using Google Maps API, and serving data to the frontend.
  - Parsing the uploaded CSV, extracting addresses, and adding a "sector" column based on predefined rules.
  - Store all file uploads, geocoded data, map settings, and user actions in a **database** (PostgreSQL or SQLite recommended).
  - Calculate **aggregations** (sum, count) per sector based on user selections.
  - Implement workspace management with **CRUD operations** (Create, Read, Update, Delete) for each flow in the database.
  - Ability to **save and load** different workspaces so users can switch between different projects.

### 3. **Database Integration:**
- A relational database (such as **PostgreSQL** or **SQLite**) will be used to store:
  - **User workspaces**, including file uploads, geocoded addresses, and current map settings.
  - Each workspace will have its own unique identifier and metadata (e.g., name, timestamp, user selections).
  - **Geocoded data** and **map visualization settings** (such as the selected thematic column and aggregation settings) will be tied to each workspace.
  - **Audit logs** for changes made within each workspace, allowing users to track changes or revert to a previous state.

### 4. **APIs and Libraries**:
- Use the **Google Maps Geocoding API** for geocoding addresses.
- **Leaflet.js** (or Google Maps API) for rendering the interactive map.
- **Pandas** for parsing and aggregating data in the backend.
- **FastAPI** framework to handle backend operations.
- **SQLAlchemy** for database interaction (CRUD operations on workspaces, geocoded data, and aggregation settings).
- **FastHTML** framework for UI rendering.

---

### **User Stories:**

#### **1. Upload CSV File:**
**As a** user,  
**I want to** upload a CSV file containing addresses,  
**So that** the application can geocode them and display the points on the map.

- **Acceptance Criteria**:
  - The user can upload a CSV file.
  - The backend processes the file, geocodes the addresses using Google Maps API.
  - A new column called "sector" is created and added automatically based on predefined rules.
  - The file and its geocoded data are saved in a unique workspace.

---

#### **2. Save Work as a Workspace:**
**As a** user,  
**I want to** save the current progress (uploaded file, geocoded data, and map settings) as a workspace,  
**So that** I can return to this project later and continue working on it.

- **Acceptance Criteria**:
  - The user can create a new workspace and save their current project (CSV, geocoded points, map settings).
  - The workspace is saved in the database with a unique identifier.
  - The user can see a list of all saved workspaces and select one to continue working on.
  - The workspace includes uploaded data, legend settings, and any custom aggregations applied.

---

#### **3. View Geocoded Points on the Map:**
**As a** user,  
**I want to** see the geocoded addresses as points on the map,  
**So that** I can visualize where all the addresses are located.

- **Acceptance Criteria**:
  - The points corresponding to each address are plotted on an interactive map.
  - The points are color-coded based on the "sector" column.
  - Map settings are saved in the workspace.

---

#### **4. Manage Workspaces:**
**As a** user,  
**I want to** create, delete, and switch between different workspaces,  
**So that** I can manage multiple datasets and geocoding flows separately.

- **Acceptance Criteria**:
  - The user can create a new workspace.
  - The user can switch between existing workspaces.
  - The user can delete a workspace if it is no longer needed.
  - Switching workspaces reloads the map and sidebar with the corresponding data and settings.

---

#### **5. View Legend with Sector Information:**
**As a** user,  
**I want to** see a legend that displays the color coding for each sector,  
**So that** I can understand how the map is thematically organized by sector.

- **Acceptance Criteria**:
  - A legend is displayed on the sidebar.
  - The legend shows each sector and its corresponding color.
  - The number of points in each sector is displayed.

---

#### **6. Select Points on the Map:**
**As a** user,  
**I want to** select one or more points on the map,  
**So that** I can view their impact on the aggregated data displayed in the legend.

- **Acceptance Criteria**:
  - The user can click or drag to select points on the map.
  - When points are selected, the aggregated data in the legend (sum and count) is updated temporarily to show the impact of the selected points.
  - Selected points are highlighted visually.

---

#### **7. Save Changes to the Workspace:**
**As a** user,  
**I want to** save the changes I made when selecting points on the map,  
**So that** the application permanently reflects the updated aggregated values.

- **Acceptance Criteria**:
  - The user can click a "Save" button to persist the changes made after selecting points on the map.
  - The backend updates the stored data in the workspace to reflect the new aggregated values.

---

#### **8. Change Aggregation Column in Legend:**
**As a** user,  
**I want to** select a different numeric column from the uploaded CSV file,  
**So that** I can see the sum and count values for that column per sector in the legend.

- **Acceptance Criteria**:
  - The user can select a different column from the CSV file for aggregation.
  - The legend updates to show the sum and count values for the selected column, aggregated by sector.
  - The new aggregation settings are saved to the workspace.

---

#### **9. Handle Errors Gracefully:**
**As a** user,  
**I want** the application to handle errors gracefully (e.g., failed geocoding or incorrect CSV format),  
**So that** I can be informed of issues without the app crashing.

- **Acceptance Criteria**:
  - The user receives clear error messages if the geocoding fails or the file format is incorrect.
  - The app continues to function even when an error occurs, allowing the user to correct the issue and try again.

---

### **Additional Considerations**:
- **Performance**: The application should handle large CSV files (up to 1000 addresses) without crashing or becoming unresponsive.
- **Security**: Input validation for the uploaded CSV file to prevent malicious data uploads.
- **Responsiveness**: Ensure that the map and sidebar are fully responsive on mobile devices.
- **Database Optimization**: Ensure efficient storage and retrieval of workspace data to maintain performance as the number of workspaces increases.

#produto  #trabalho #geoexpert #PRD