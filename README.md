# VIN Validator & Reporting System

A Laravel-based reporting and VIN validation system that provides a foundation for building custom reports, data exports, and analytics.  
This project is structured with flexibility in mind, making it easy to extend with additional modules or integrate into existing applications.

---

## 🚀 Features
- Built with **Laravel 11** (latest stable release)
- **VIN validation** module included
- Modular structure for reporting
- RESTful API support
- Authentication scaffolding (Laravel Breeze/Jetstream)
- Example report generators included

---

## 🛠️ Installation

Follow these steps to set up the project locally:

### 1. Clone the repository
```bash
git clone https://github.com/m-hassan007/vin-validator.git
cd vin-validator


2. Install dependencies
composer install
npm install && npm run build

3. Set up environment



VIN Validation

POST /api/v1/vin/validate

Request Example:

curl -X POST http://127.0.0.1:8000/api/v1/vin/validate \
     -H "Accept: application/json" \
     -H "Content-Type: application/json" \
     -d '{"vin":"1HGCM82633A123456"}'


Response Example:
{
  "valid": true,
  "vin": "1HGCM82633A123456",
  "message": "VIN is valid."
}


2. Reports

GET /api/v1/reports

Request Example:

curl -X GET http://127.0.0.1:8000/api/v1/reports \
     -H "Accept: application/json"


Response Example:

[
  {
    "id": 1,
    "title": "Monthly VIN Validation Report",
    "created_at": "2025-08-31T10:20:00Z"
  }
]
