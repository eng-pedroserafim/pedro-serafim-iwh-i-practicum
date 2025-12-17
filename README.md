# Integrating With HubSpot I: Foundations Practicum
This practicum is one of two requirements for receiving the **Integrating With HubSpot I: Foundations certification**.  

## Author
PEDRO SERAFIM GOMES NETO

---

**HubSpot developer test account custom object list view:**  
https://app.hubspot.com/contacts/50806986/objects/2-54449633/views/all/list

**Github repository:** 
This repository is for the **Integrating With HubSpot I: Foundations** course.   
https://github.com/eng-pedroserafim/pedro-serafim-iwh-i-practicum

---

## Practicum Summary
This project is a **Node.js application** built to fulfill all technical and procedural requirements defined in the Integrating With HubSpot I: Foundations practicum.

The implementation demonstrates the complete lifecycle of a simple HubSpot integration:
- CRM data modeling
- API authentication using a private app
- Data retrieval and creation via HTTP requests
- Server-side rendering using templates
- Secure handling of credentials
- Incremental development with version control


## Project Overview
The project was developed and validated using a **HubSpot Developer Test Account**, as required.

This Node.js application integrates with the HubSpot CRM API using a **private app** and showcases several key features:
- **Custom Object Integration**: The application works with a custom CRM object called **Cars**, which has custom properties like Name, Brand, and Plate.
- **Display Data**: It retrieves and displays these custom object records in a structured HTML table.
- **Form Submission**: It allows users to submit new records using a form, which will be created in HubSpot.
- **Environment Variables**: Sensitive credentials, like the private app access token, are managed using **dotenv**.

---

## Custom Object Implementation - Cars
A custom CRM object was created to satisfy the practicum requirements.
The project utilizes a custom CRM object called **Cars**. This object contains the following fields:

- **Name**: The name of the car (string).
- **Brand**: The manufacturer of the car (string).
- **Plate**: The registration plate number (string).

This custom object is linked to **Contacts** within the HubSpot CRM. The association between the custom object and contacts enables relevant data to be organized and accessed across different areas of the CRM.

**Object details:**
- **Object name:** Cars
- **Primary display property:** Name
- **Additional custom properties:**
  - Brand
  - Plate
- **Associations:** Associated with Contacts
- **Creation method:** HubSpot Data Model Builder (UI)

The object was populated with multiple records and validated both through the HubSpot UI and through API calls made by the application.

---

## Application Behavior
The Node.js application integrates directly with the HubSpot CRM API using a **private app access token**.

The application supports the following behaviors:

- Fetching custom object records using the CRM Objects API
- Rendering retrieved records in a tabular format using Pug templates
- Creating new custom object records through an HTML form
- Redirecting users after successful record creation
- Handling API authentication securely via environment variables

---

## Routes Implemented
| Route | Method | Description |
|------|--------|-------------|
| `/` | GET | Retrieves all Cars records from HubSpot and renders them in a table |
| `/update-cobj` | GET | Renders a form to create a new Cars record |
| `/update-cobj` | POST | Creates a new Cars record via the HubSpot API and redirects to the homepage |

These routes demonstrate correct usage of HTTP methods, request handling, and API interaction using Express and Axios.

### Route 1: `/`
- **Purpose**: This route displays all records for the custom object **Cars** in an HTML table.
- **Implementation**: It fetches records from the HubSpot CRM API using the GET method and passes them to a Pug template (`homepage.pug`), which renders the table dynamically.

### Route 2: `/update-cobj` (GET)
- **Purpose**: This route renders a form to create new records for the custom object **Cars**.
- **Implementation**: The form contains fields for the three properties: **Name**, **Brand**, and **Plate**. It uses the Pug template (`updates.pug`) to display the form.

### Route 3: `/update-cobj` (POST)
- **Purpose**: This route handles the POST request to submit data from the form.
- **Implementation**: When the user submits the form, the app makes a POST request to the HubSpot API to create a new custom object record. Upon success, the user is redirected to the homepage.


---

## Technology Stack
- **Node.js** – JavaScript runtime (https://nodejs.org/en/download)
- **Express** – Routing and application framework (https://expressjs.com/en/starter/installing.html)
- **Axios** – HTTP client for HubSpot API calls (https://axios-http.com/docs/intro)
- **Pug** – Server-side templating engine (https://pugjs.org/api/getting-started.html)
- **dotenv** – Environment variable management
- **Git & GitHub** – Version control and collaboration (https://product.hubspot.com/blog/git-and-github-tutorial-for-beginners)

---

## Environment Variables
Sensitive credentials are managed using environment variables.

The following variables are required:

```
PRIVATE_APP_ACCESS_TOKEN=your_private_app_access_token_here
CUSTOM_OBJECT_TYPE=2-54449633
```

The `.env` file is excluded from version control via `.gitignore` to ensure credentials are never committed.

---

## Running the Application Locally
1. Install dependencies:
   ```
   npm install
   ```

2. Start the server:
   ```
   node index.js
   ```

3. Open a browser and navigate to:
   ```
   http://localhost:3000
   ```

From the homepage, users can view existing Cars records and add new records via the provided form.

---

## Commit Log / Delivery Notes: Development and Version Control Practices
This repository reflects professional development practices:

- [✓] Setup repo + branch workflow
- [✓] Add dotenv + env-based auth
- [✓] Implement GET / listing Cars
- [✓] Implement GET+POST /update-cobj create record
- [✓] Add Pug templates + CSS improvements
- [✓] Add client-side validation for plate
- [✓] Document usage + security notes

Commit history was intentionally maintained to demonstrate progress and adherence to the practicum instructions.

---

## Practicum Requirements Checklist
The following checklist documents how each practicum requirement was addressed:

- [✓] HubSpot Developer Test Account created
- [✓] Private app created with required permissions
- [✓] Custom CRM object created with at least three properties
- [✓] Custom object associated with Contacts
- [✓] Multiple records created and validated
- [✓] Node.js application created using Express
- [✓] Axios used to make authenticated API calls
- [✓] GET route implemented to retrieve CRM data
- [✓] POST route implemented to create CRM records
- [✓] Pug templates used to render views
- [✓] Environment variables used for secure authentication
- [✓] Private app token excluded from the repository
- [✓] Incremental Git commits demonstrating development progress