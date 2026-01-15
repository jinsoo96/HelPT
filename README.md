# HelPT

## Generative AI-based QR Code System for Personalized Patient Health Information

> Presented at 2023 Korea Knowledge Management Society Fall Conference - Idea Competition

[![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)](https://python.org)
[![Django](https://img.shields.io/badge/Django-4.1-green.svg)](https://djangoproject.com)
[![LangChain](https://img.shields.io/badge/LangChain-Latest-orange.svg)](https://langchain.com)
[![OpenAI](https://img.shields.io/badge/OpenAI-GPT--4-purple.svg)](https://openai.com)

---

## Overview

**HelPT** is a system that generates QR codes containing personalized health information using patient medical data. By combining Generative AI (GPT-4) with the LangChain framework, the system analyzes patient input and converts customized health information into QR codes for easy access.

### Key Features

- **Real-time Health Information Access**: Patients can check their health status anytime, anywhere
- **Intuitive Interface**: Simple web-based QR code generation
- **AI-powered Analysis**: Personalized health information using LangChain + GPT-4
- **Enhanced Security**: Secure data transmission via QR codes

---

## Project Structure

```
HelPT/
├── README.md                 # Project documentation
├── requirements.txt          # Python dependencies
├── .gitignore               # Git ignore file
├── .env.example             # Environment variables template
├── LICENSE                  # MIT License
│
├── docs/                    # Documentation
│   └── presentation.pdf     # Presentation slides
│
├── data/                    # Sample data
│   └── sample_medical_records.csv
│
└── src/                     # Source code
    └── qrsite/
        ├── manage.py
        ├── qrsite/          # Django project settings
        │   ├── settings.py
        │   ├── urls.py
        │   └── wsgi.py
        │
        └── polls/           # Main application
            ├── views.py     # View logic
            ├── models.py    # Data models
            ├── urls.py      # URL routing
            ├── agents.py    # LangChain agents
            ├── agent_config.py  # Agent configuration
            ├── tools.py     # QR code generation tool
            ├── parsers.py   # Output parser
            └── templates/   # HTML templates
                ├── home.html
                └── result.html
```

---

## Tech Stack

| Category | Technology | Description |
|----------|------------|-------------|
| **Backend** | Django 4.1 | Web framework |
| **AI Model** | GPT-4 (OpenAI) | Generative AI model |
| **AI Framework** | LangChain | LLM application development framework |
| **QR Code** | qrcode | QR code generation library |
| **Database** | SQLite | Data storage |

---

## Quick Start

### 1. Clone the Repository

```bash
git clone git@github.com:jinsoo96/HelPT.git
cd HelPT
```

### 2. Create and Activate Virtual Environment

```bash
python -m venv venv

# Windows
venv\Scripts\activate

# macOS/Linux
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Set Environment Variables

```bash
# Copy .env.example to .env
cp .env.example .env

# Open .env file and set your OpenAI API key
OPENAI_API_KEY=your-api-key-here
```

### 5. Run Database Migrations

```bash
cd src/qrsite
python manage.py migrate
```

### 6. Start the Server

```bash
python manage.py runserver
```

### 7. Access in Browser

```
http://127.0.0.1:8000/
```

---

## System Architecture

```
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│   User Input    │────▶│   LangChain     │────▶│    GPT-4       │
│  (Symptoms)     │     │   Agent         │     │   Analysis      │
└─────────────────┘     └─────────────────┘     └─────────────────┘
                                                        │
                                                        ▼
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│   QR Code       │◀────│   QR Code       │◀────│   Health Info   │
│   Display       │     │   Generation    │     │   Summary       │
└─────────────────┘     └─────────────────┘     └─────────────────┘
```

---

## Key Features

### 1. Health Status Input
Users can input their current symptoms or health conditions through the web interface.

### 2. AI Analysis
The LangChain agent utilizes GPT-4 to analyze the input and generate personalized health information.

### 3. Medical Data Integration
Combines existing medical records (CSV) with user input to generate comprehensive health information.

### 4. QR Code Generation
Converts analyzed health information into QR codes for quick access by healthcare providers.

---

## Sample Data Format

```csv
Date,Visit Type,Diagnosis,Medications,Treatment
2023-01-03,Checkup,Hypertension,Tamiflu,Examination
2023-01-09,Hospital Visit,Cold,"Diabetes medication, Antibiotics",X-ray
...
```

---

## Expected Benefits

### Qualitative Effects
- Improved efficiency for healthcare professionals
- Enhanced security through QR code-based data transmission
- Integration of medical data with generative AI

### Quantitative Effects
- Reduced consultation time and medical costs
- Increased utilization of medical data
- Improved communication between patients and healthcare providers

---

## Contact

For questions or collaborations:

**Author:** Kim Jin Soo, Kang Minsuk, Kang Seyoung, Jo Yoonju  

**GitHub:** [@jinsoo96](https://github.com/jinsoo96), [@minsuk1003](https://github.com/minsuk1003), [@strongeryoung](https://github.com/strongeryoung), [@justlikeazoo](https://github.com/justlikeazoo)

---

## References

For presentation materials and references, please refer to the `docs/` folder.

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
