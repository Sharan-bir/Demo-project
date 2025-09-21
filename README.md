# Django Jobs Backend

This is the backend for the Jobs application. Built with **Django** and **Django REST Framework**, it supports candidate data submission and resume uploads.  

---

## Features

- REST API endpoint to create candidates with:
  - Name, Address, Skills, GitHub link, Age, Email, Phone number
  - College Name and Passing Year
  - Resume upload (PDF/DOC/DOCX)
- Validation for email, numeric fields, and resume file type/size
- Admin dashboard for managing candidates
- Export candidate list to Excel/CSV
- CORS enabled for frontend integration
- Whitenoise for static file serving
- Docker-ready
- SQLite database (default Django DB)

---

## Prerequisites

- Python 3.12+
- Git
- Docker (optional)

---

## Quick Start (Local Development)

### 1. Clone the repository

```bash
git clone https://github.com/yourusername/yourrepo.git
cd yourrepo
