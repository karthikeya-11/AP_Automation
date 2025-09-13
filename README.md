## 🏗️ **System Architecture**

```
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│   File Upload   │────▶│  FastAPI Backend│────▶│ Google Document │
│   (Streamlit)   │     │   Validation    │     │      AI         │
└─────────────────┘     └─────────────────┘     └─────────────────┘
         │                       │                       │
         │                       ▼                       ▼
         │              ┌─────────────────┐     ┌─────────────────┐
         │              │   File Storage  │     │  Data Extraction│
         │              │   (Optional)    │     │  & Processing   │
         │              └─────────────────┘     └─────────────────┘
         │                       │                       │
         └───────────────────────┼───────────────────────┘
                                 ▼
                    ┌─────────────────────────────────────┐
                    │         Results Display             │
                    │   • Vendor Info  • Financial Data  │
                    │   • Line Items   • Confidence      │
                    │   • Analytics    • Export Options  │
                    └─────────────────────────────────────┘
```


## 🚀 **Quick Start**

### **Prerequisites**
- Python 3.8+
- Google Cloud Account with Document AI enabled
- Git
- Docker (optional)

### **1. Clone Repository**
```bash
git clone  --
cd invoice-processing-ai
```

### **2. Install Dependencies**
```bash
pip install -r requirements.txt
```

### **3. Google Cloud Setup**
```bash
# Set up environment variables
cp .env.example .env

# Edit .env with your credentials:
# GCP_PROJECT_ID=your-project-id
# GCP_LOCATION=us
# GCP_PROCESSOR_ID=your-processor-id
# GOOGLE_APPLICATION_CREDENTIALS=path/to/your/key.json
```

### **4. Run Application**
```bash
# Terminal 1: Start API Backend
cd src/api
python main.py

# Terminal 2: Start Frontend
cd frontend
streamlit run app.py
```

### **5. Access Application**
- **Frontend**: http://localhost:8501
- **API Documentation**: http://localhost:8000/docs
- **Health Check**: http://localhost:8000


## 📁 **Project Structure**

```
invoice-processing-ai/
├── 📂 src/
│   ├── 📂 api/                     # FastAPI backend
│   │   └── main.py                  # API entry point
│   └── 📂 utils/                   # Configuration & utilities
│       └── config.py               # Settings management
├── 📂 frontend/                    # Streamlit web interface
│   └── app.py                      # Main application
├── 📂 .github/                     # CI/CD & automation
│   ├── workflows/ci-cd.yml         # GitHub Actions
│   └── dependabot.yml              # Dependency updates
├── 📂 helm/                       # Kubernetes Helm charts
│   ├── Chart.yaml                  # Helm chart definition
│   └── values.yaml                 # Configuration values
├── 📂 k8s/                        # Kubernetes manifests
│   └── deployment.yml              # K8s deployment
├── 📂 monitoring/                  # Observability
│   └── prometheus.yml              # Monitoring config
├── 📂 tests/                      # Test suite
├── docker-compose.yml             # Multi-container setup
├── Dockerfile                     # Container definition
├── requirements.txt               # Python dependencies
├── .env.example                   # Environment template
├── nginx.conf                     # Reverse proxy config
└── README.md                      # This file
```

## 🎯 **Use Cases**

### **Enterprise Applications**
- **Accounts Payable Automation** - Streamline invoice processing workflows
- **Financial Data Entry** - Eliminate manual data entry errors
- **Audit & Compliance** - Maintain accurate financial records
- **ERP Integration** - Feed structured data into enterprise systems

### **Business Benefits**
- **Cost Reduction** - Reduce processing costs by 90%
- **Time Savings** - Process invoices in seconds, not minutes
- **Accuracy Improvement** - Eliminate human data entry errors
- **Scalability** - Handle volume spikes without additional staff
- **Compliance** - Standardized data extraction and audit trails

## 🔧 **Configuration**

### **Environment Variables**
```bash
# Google Cloud Configuration
GCP_PROJECT_ID=your-project-id
GCP_LOCATION=us
GCP_PROCESSOR_ID=your-processor-id
GOOGLE_APPLICATION_CREDENTIALS=path/to/credentials.json

# API Configuration
API_HOST=0.0.0.0
API_PORT=8000
DEBUG=true

# File Upload Configuration
MAX_FILE_SIZE=10485760  # 10MB
UPLOAD_DIR=uploads
```
