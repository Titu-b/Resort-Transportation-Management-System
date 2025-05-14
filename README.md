# Resort Transportation Management System (RTMS)

A distributed cloud-based transportation management system developed as part of the COE892: Distributed and Cloud Computing course at Toronto Metropolitan University (Winter 2025). The RTMS optimizes resort cart dispatch by managing guest transportation requests, real-time cart scheduling, and data communication using secure APIs and modern backend architecture.

## Features

- Real-time ride request handling and vehicle assignment
- REST and gRPC-based backend with role-based access
- PostgreSQL database with Sequelize ORM integration
- Redis caching for active ride requests and fast lookups
- Secure deployment using HTTPS via Caddy reverse proxy
- Admin-facing web interface with Bootstrap & JavaScript
- Swagger UI documentation and WebSocket notifications
- Hosted on Oracle Cloud Linux VM with TLS enabled

## Project Architecture

- **Frontend:** HTML, JavaScript, Bootstrap, Fetch API, Jinja2 (in earlier versions)
- **Backend:** Node.js + Express.js (final), gRPC (initial), Sequelize ORM
- **Database:** PostgreSQL, designed for transport logistics (vehicle, requests, destinations, transfers)
- **Caching:** Redis
- **Deployment:** Oracle Cloud Infrastructure (24 GB RAM, 4 vCPUs), Caddy Server, DNS via Porkbun

## Backend Modules

- **Destination Module:** Add/edit resort locations
- **Vehicle Module:** Create/update vehicle details (capacity, availability, current location)
- **Passenger Request Module:** Submit ride requests, handle urgent flags
- **Transfer Module:** Create and complete transfers, manage assignments

Each module follows a layered architecture:
- **Controller** → handles requests
- **Service** → applies business logic
- **Model** → interfaces with PostgreSQL via Sequelize

## Frontend Features

- Vehicle creation and status display
- Destination setup and live data population
- Ride request form with real-time updates
- Dynamic dropdowns and "View All" admin panel
- Responsive layout for receptionists and staff

## API Documentation

- Accessed via Swagger UI on the `/docs` endpoint
- Full request/response bodies, schema validation via Celebrate + Joi

## Deployment & Domain

- **Domain:** [https://applejuicer.dev](https://applejuicer.dev)
- Caddy server provides HTTPS with Let’s Encrypt TLS certificates
- Frontend accessed via `/COE892`; backend via `/api`
- Ports 3000 (backend) and 5500 (frontend) reverse proxied through Caddy

## How to Run Locally

1. Clone the repository and navigate into the project directory.
2. Set up PostgreSQL and Redis locally (or use Docker).
3. Install backend dependencies:


4. Run backend:

5. Open `frontend/index.html` in a browser or serve using a simple HTTP server.

## Contributions

- **Tala Baaj** – Frontend developer, UI/UX, frontend-backend integration, system testing
- **Ali AJ Parasteh** – Cloud deployment, Caddy & Oracle VM setup
- **Parsa Pourmand** – Backend API and system integration
- **Amir Rezaei** – Database management, backend data processing, project management
