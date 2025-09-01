# VIN Validator & Reporting System

A Laravel-based reporting and VIN validation system that provides a foundation for building custom reports, data exports, and analytics.  
This project is structured with flexibility in mind, making it easy to extend with additional modules or integrate into existing applications.

---

## 🔍 Handling VIN Mistakes (Points 2 & 3)

When customers copy their VINs, they often make mistakes. Based on analysis, here are the most common ones:

1. **Character Confusion**  
   - Mistaking `O` for `0`, `I` for `1`, or `Q` for `0`.  
   - ✅ We can reliably correct these by substitution.

2. **Missing Characters (16 digits instead of 17)**  
   - A digit/letter may be skipped when typing.  
   - ✅ We can insert candidates in different positions and validate.

3. **Extra Characters (18 digits instead of 17)**  
   - Copy-paste or double-typing errors.  
   - ✅ We can try removing one character at a time and revalidating.

4. **Transposed Characters**  
   - Two adjacent characters swapped accidentally.  
   - ✅ We can detect by swapping pairs and checking validity.

👉 Realistically, corrections 1–3 are the most common and easiest to fix automatically.  
Correction 4 (swapped chars) is supported but may yield multiple suggestions.

---

### 💡 VIN Correction Function
When a VIN is invalid, the system tries to generate valid alternatives using the above rules.  
This is implemented in a `VinCorrectionService`, which integrates with the validator.

**Example CURL Request with Suggestions**

```bash
curl -X POST http://127.0.0.1:8000/api/v1/vin/validate \
  -H "Accept: application/json" \
  -H "Content-Type: application/json" \
  -d '{"vin": "1HGCM82633A00435O"}'


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
