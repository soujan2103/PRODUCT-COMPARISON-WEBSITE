# Modern Product Comparison Website

A React-based web application for comparing tech products across different e-commerce platforms.

## Prerequisites

1. Node.js (v14 or higher)
2. MySQL Server
3. VS Code
4. Git

## Installation Steps

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd tech-compare
   ```

2. **Install dependencies**
   ```bash
   npm install

   - ESLint  npm init @eslint/config@latest
     - Prettier  npm i prettier
     - Tailwind CSS IntelliSense  npm i tailwindcss
       npm install @types/node
   ```

3. **Set up MySQL Database**
   
   a. Install MySQL Server if not already installed
   b. Create a new database:
   ```sql
   CREATE DATABASE tech_compare;
   ```
   mysql -u root -p
   c. Import the schema:
   ```bash
   mysql -u root -p tech_compare < server/db/schema.sql
   ```

4. **Configure Environment Variables**
   
   Create a `.env` file in the root directory:
   ```
   DB_HOST=localhost
   DB_USER=root
   DB_PASSWORD=your_password
   DB_NAME=tech_compare
   PORT=5000
   ```

5. **Start the Backend Server**
   ```bash
   # In one terminal
   npm run server
   ```

6. **Start the Frontend Development Server**
   ```bash
   # In another terminal
   npm run dev
   ```

7. **Access the Application**
   - Frontend: http://localhost:5173
   - Backend API: http://localhost:5000

## Project Structure

```
src/
├── components/     # React components
├── data/          # Static data and types
├── services/      # API services
├── store/         # State management
└── types/         # TypeScript types

server/
├── api/           # Express API routes
├── db/            # Database configuration
└── utils/         # Utility functions
```

## Available Scripts

- `npm run dev`: Start frontend development server
- `npm run server`: Start backend server
- `npm run build`: Build for production
- `npm run preview`: Preview production build

## Database Schema

### Users Table
- id (Primary Key)
- name
- email (Unique)
- password (Hashed)
- created_at

### Categories Table
- id (Primary Key)
- name
- slug (Unique)

### Products Table
- id (Primary Key)
- title
- price
- description
- brand
- image_url
- category_id (Foreign Key)
- platform
- external_url
- created_at

## API Endpoints

### Users
- POST /api/users/register - Register new user
- POST /api/users/login - User login

### Products
- GET /api/products - Get all products
- GET /api/products/search - Search products
- GET /api/products/category/:slug - Get products by category

## Technologies Used

- React 18
- TypeScript
- Tailwind CSS
- Express.js
- MySQL
- React Router
- Zustand (State Management)
- Lucide Icons