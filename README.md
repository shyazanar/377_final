## Nearby Mental Health Resource Finder
Project Description
This web application helps users find nearby mental health resources, specifically psychotherapists, using the user's current location. It integrates OpenStreetMap's map interface with backend data served from a Supabase database. Users can view mental health resources near them and add new resources to the database. The app dynamically expands its search radius until it finds at least one resource.

# The system consists of:

A front-end that displays an interactive map with nearby mental health resources.

A backend API connected to a Supabase database with two endpoints:

GET /api/resources — Retrieves all mental health resources.

POST /api/add-resource — Adds a new resource to the database.

# Target Browsers
Desktop browsers: Latest versions of Chrome, Firefox, Edge, Safari.

Mobile browsers: iOS Safari, Android Chrome.

The app uses HTML5 Geolocation API, so browsers must support this feature.

Responsive design intended for desktop and mobile screen sizes.

## Developer Manual

# Setup and Installation

1. **Clone the repository:**

   ```bash
   git clone https://your-repository-url.git
   cd your-project-folder
   
2. **Instal Backend Dependencies**
   cd backend
npm install

3. **Configure environment variables:**
   SUPABASE_URL=your-supabase-url
SUPABASE_KEY=your-supabase-service-role-key
PORT=3000

4. **Setup Supabase database:**
Create a table named mental_health_resources with the following columns:
- id (primary key, auto-increment integer)
- name (text)
- latitude (float)
- longitude (float)
- type (text)

5. **Start the Backend Server:**
   npm start

6. **Open the frontend:**
The frontend is a static HTML and JavaScript app located in the root folder. You can:

Open index.html directly in your browser, or

Serve it using any static file server (e.g., VSCode Live Server, http-server, etc.)

## API Endpoints
GET /api/resources
Returns a JSON array of all mental health resources from the database.

Each resource object includes:
   -id — integer
   -name — string
   -latitude — float
   -longitude — float
   -type — string

## POST
Adds a new mental health resource to the database.

Expects JSON request body:

json
Copy
Edit
{
  "name": "Resource Name",
  "latitude": 38.8951,
  "longitude": -77.0364,
}

## Known Bugs and Roadmap
- No input validation or authentication on the POST endpoint.
- No offline map support.
- Lack of automated tests.
