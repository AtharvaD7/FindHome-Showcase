# 🏡 FindHomeJ - Next-Gen Real Estate Platform

[![Status: Production](https://img.shields.io/badge/Status-Production-success.svg)]()
[![Frontend: React](https://img.shields.io/badge/Frontend-React-blue.svg)]()
[![Backend: Spring Boot](https://img.shields.io/badge/Backend-Spring_Boot-green.svg)]()
[![DB: PostgreSQL](https://img.shields.io/badge/DB-PostgreSQL-blue.svg)]()

> **Note:** This repository serves as an architectural showcase and documentation hub for **FindHomeJ**. The core application source code is maintained in a private repository to protect proprietary API orchestrations, custom AI prompts, and security implementations.

**[🚀 View Live Project Here](#)** *(https://find-home-realty.vercel.app/)*

---

## 📖 Overview

FindHomeJ is a comprehensive, full-stack real estate platform designed to modernize the property search experience. Going beyond standard CRUD operations, it integrates advanced LLM orchestration (Google Gemini API) to provide intelligent property insights, automated image processing via Cloudinary, and a robust Role-Based Access Control (RBAC) system for administrators and standard users.

## ✨ Core Features

*   **🧠 AI-Powered Insights:** Leverages the Google Gemini API to analyze property details and generate intelligent summaries and recommendations for buyers.
*   **🏢 Robust Property Management:** End-to-end lifecycle management for listings, powered by a Spring Boot backend and PostgreSQL.
*   **🖼️ Automated Media Handling:** Seamless integration with Cloudinary for optimized, secure image uploads and delivery.
*   **🛡️ Enterprise-Grade Security:** Comprehensive JWT-based authentication coupled with strict Role-Based Access Control (RBAC).
*   **🚦 Intelligent Rate Limiting:** Custom global rate limiters implemented to protect AI API endpoints and ensure system stability.

## 📐 System Architecture

The application is built on a decoupled architecture, ensuring scalability and clear separation of concerns.

<img width="1440" height="1640" alt="image" src="https://github.com/user-attachments/assets/9fffd2b6-3cba-43cd-b047-e7ff41199f1f" />


```mermaid
graph TD
    Client[React Frontend / Vite] -->|HTTPS / REST| API[Spring Boot API Gateway]
    
    subgraph Backend Infrastructure
        API --> Auth[JWT Security Layer]
        Auth --> Service[Business Logic Services]
        Service --> DB[(PostgreSQL Database)]
    end
    
    subgraph External Services
        Service -->|Media Uploads| Cloudinary[Cloudinary Cloud]
        Service -->|AI Prompts| Gemini[Google Gemini API]
    end
```

## 🛠️ Technical Stack

### Frontend
*   **Framework:** React (Vite)
*   **Styling:** Modern CSS / Context API for state management
*   **Routing:** React Router

### Backend
*   **Framework:** Java / Spring Boot 3
*   **Database:** PostgreSQL with Hibernate/JPA
*   **Security:** Spring Security + JWT
*   **External APIs:** Google Gemini (AI Insights), Cloudinary (Media)
*   **Cloud:** Render(Backend), Vercel(frontend), NeonDB(Serveless PostgesSQL DB)

## 📸 Application Showcase

### 📍 AI Property Neighborhood Insights
> Demonstrating the Gemini API orchestration to provide users with intelligent property surroundings context.
![AI Insights Demo](./assets/AiNeighborhood-page.png)

### 📈 AI Makrtet Insights
> Demonstrating the Gemini API orchestration to provide users with intelligent market context.
![Market Insights Demo](./assets/MarketInsightsScreenShot.png)

### 🔍 Property Exploration
> A highly optimized frontend consuming REST APIs for real-time property discovery.
![Property Search](./assets/propsearch-page.png)

### 📋 Property Details Page
> A highly optimized frontend consuming REST APIs for knowing property details.
![Property Search](./assets/DemoPropDetails.png)

### 📑 Listing Page
> Property listings action page.
![Property Search](./assets/sell-page.png)

### 📝 Listing Details Form
> Comprehensive Property details form consisting almost all information fields.
![Property Search](./assets/ListForm-page.png)

### 👨‍💼 Agent Dashboard
> Property Lister / Agent dashboard for managing listings and inquiries.
![Agent Dashboard](./assets/agentDashInquiry.png)

### ⚙️ Admin Dashboard 
> Secure RBAC dashboard for managing global settings, rate limits, and users.
![Admin Dashboard](./assets/adminDashboardKpis.png)

### 📨 Admin Dashboard Property Listing Requests
> Separate tab for managing incoming listing approval requests.
![Admin Dashboard](./assets/AdminPropRequests.png)

## 💡 Engineering Impact & Highlights

*   **API Orchestration & Efficiency:** Designed a custom wrapper around the Gemini API, utilizing global rate limiting algorithms (`GlobalGeminiRateLimiter`) to prevent quota exhaustion while maintaining sub-second response times for users.
*   **Secure Content Delivery:** Architected a seamless pipeline between the frontend client and Cloudinary, offloading heavy media processing from the primary Spring Boot server, resulting in faster load times.
*   **Scalable Authorization:** Implemented stateless session management using JWTs, ensuring that administrative endpoints and sensitive user data remain protected behind strict validation layers.

---
*If you are a recruiter or engineer interested in discussing the technical implementation details, please feel free to reach out via my*
**[LinkedIn](#)** *([https://www.linkedin.com/in/atharva-deshmukh-93737a252/])*
**[Gmail](#)** *([datharva706@gmail.com])*
