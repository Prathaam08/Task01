# 🚚 KartBuddy Frontend Documentation

## 🧭 Project Overview
**KartBuddy** is a comprehensive logistics and transportation management platform built using **React**, **Redux Toolkit**, and other modern web technologies.  
The application supports multiple user roles — **customers**, **drivers**, **vendors**, **sales personnel**, and **administrators** — creating a full ecosystem for logistics operations and management.

---

## 🧱 Technology Stack
| Category | Technology |
|-----------|-------------|
| **Frontend Framework** | React 19.1.0 with Vite |
| **State Management** | Redux Toolkit + RTK Query |
| **UI Libraries** | Material-UI, Tailwind CSS, Framer Motion |
| **Maps Integration** | Google Maps API, Leaflet |
| **Charts** | Chart.js |
| **Build Tool** | Vite |
| **Package Manager** | npm |

---

## 📦 Key Dependencies
- `@reduxjs/toolkit` – State management and API handling  
- `@mui/material` – UI components  
- `react-router-dom` – Client-side routing  
- `axios` – HTTP client  
- `react-leaflet` – Map visualization  
- `jspdf` – PDF generation  
- `react-toastify` – Notifications  

---

## 🧩 Architecture Overview

### Folder Structure

```
src/
├── lib/
│ ├── api/ # RTK Query API definitions
│ ├── auth/ # Authentication state management
│ ├── store/ # Redux store configuration
│ └── utils/ # Helper functions
├── routes/
│ ├── AdminDashboard/ # Admin interface
│ ├── CustomerDashboard/ # Customer interface
│ ├── DriverDashboard/ # Driver interface
│ ├── SalesDashboard/ # Sales interface
│ └── VendorDashboard/ # Vendor interface
└── utils/ # Global utilities

```

---

## ⚙️ State Management

### Redux Store Configuration
- Configured via `configureStore()` from Redux Toolkit  
- Middleware includes **RTK Query** and serializable checks  
- Persistent state with **redux-persist**

### Authentication State (`authSlice.js`)
- Manages login/logout and JWT tokens  
- Stores user profile data  
- Persists session data in `localStorage`

### API Layer (`apiSlice.js`)
- Centralized API with **RTK Query**  
- Automatic caching & invalidation  
- Auth header injection and token refresh handling  

---

## 🛣️ Routing Architecture
- **Protected Routes** via `ProtectedRoute` component  
- Redirects unauthenticated users to `/login`  
- Routes by role:
  - `/admin-dashboard/*`
  - `/customer-dashboard/*`
  - `/driver-dashboard/*`
  - `/sales-dashboard/*`
  - `/vendor-dashboard/*`

---

## 🖥️ Dashboard Components

### 🧑‍💼 Admin Dashboard
**Purpose:** Complete administrative control  
**Features:**
- Order & Trip Management  
- User directories (customers, drivers, vendors)  
- Finance, HR, and Sales Management  
- Marketing & Analytics Tools  

**Data Flow:** Uses multiple RTK Query endpoints, cache invalidation, and filtering.

---

### 🧍 Customer Dashboard
**Purpose:** Booking and tracking shipments  
**Features:**
- Place Orders (multi-step, dynamic pricing)  
- Track Order History  
- Wallet & Address Management  
- Customer Support  
**Data Flow:** LocalStorage + API sync for real-time updates.

---

### 🚗 Driver Dashboard
**Purpose:** Manage assigned trips and deliveries  
**Features:**
- Online/Offline toggle  
- Real-time trip tracking  
- Delivery history  
- Syncs with backend for updates  

---

### 💼 Sales Dashboard
**Purpose:** Lead & customer management  
**Features:**
- Lead and CRM tools  
- Sales analytics  
- Daily visit tracking  

---

### 🏢 Vendor Dashboard
**Purpose:** Manage fleet and vendor data  
**Features:**
- Driver & Vehicle Management  
- Reports and Analytics  
- Profile synchronization  

---

## 💡 Core Business Logic

### Order Management System
- Real-time tracking using **Google Maps**  
- Order filtering, hub-based assignment  
- API integration for route optimization  

### Address Management
- CRUD operations for saved addresses  
- Local persistence + API synchronization  

### Authentication Flow
- JWT-based auth  
- Auto-refresh on 401  
- Protected routing + role checks  

---

## 🌐 API Integration
### RTK Query Endpoints
- **Auth:** Login, Register, Profile  
- **Orders:** CRUD, History, Tracking  
- **Wallet:** Balance, Transactions  
- **Users:** Customer, Driver, Vendor, Staff  
- **Finance:** Payments, Refunds, Coupons  
- **Location:** Address and DC services  

**Data Flow:**  
`User Action → Component → RTK Query → API → Redux Store → UI Update → Local Storage (Cache)`

---

## 🛡️ Security Implementation
- JWT authentication  
- Role-based route protection  
- Encrypted API requests  
- Sensitive data never stored locally  

---

## ⚡ Performance Optimizations
- **RTK Query:** intelligent caching, background refetch  
- **Lazy loading** dashboard components  
- **React.memo** for render optimization  
- **Optimistic updates** for fast UI response  

---

## 📚 Key Modules Summary
| Module | Purpose | Why Used |
|--------|----------|----------|
| **lib/store/** | Centralized state | Predictable state, caching |
| **lib/api/** | API communication | Caching, error handling |
| **lib/auth/** | Authentication | Secure, session control |
| **utils/** | Helper functions | Code reusability |
| **routes/** | Role dashboards | Modular UI structure |

---

## 💾 Data Sources
- **Backend API** – via RTK Query  
- **Local Storage** – preferences, caching  
- **Redux Store** – global state  
- **External APIs** – Google Maps, Payment gateways  

---

## 🏁 Conclusion
KartBuddy Frontend represents a **scalable, modular, and performance-optimized logistics platform**.  
Built with **React** and **Redux Toolkit**, it ensures efficient state handling, secure authentication, and smooth user experience across all dashboards.  
With **RTK Query** for data management and **modular architecture** for user roles, the project achieves maintainability, scalability, and flexibility — ready for enterprise deployment.

---

**Repository:** [KartBuddy Frontend v3](https://github.com/KartBuddy/kartbuddy-frontend-v3)  

