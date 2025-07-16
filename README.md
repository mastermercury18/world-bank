# Quantum-Enhanced Climate Risk Insurance Model

**Team:** Quantum HQ  
**Phase:** 3 Implementation for World Bank Global Industry Challenge 2025

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Architecture](#architecture)
- [Technology Stack](#technology-stack)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Data Simulation](#data-simulation)
- [Quantum Pipeline](#quantum-pipeline)
- [Classical ML Pipeline](#classical-ml-pipeline)
- [API Endpoints](#api-endpoints)
- [Usage Examples](#usage-examples)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## Overview
The Quantum-Enhanced Climate Risk Insurance Model leverages both quantum computing algorithms and classical machine learning techniques to provide faster, more accurate assessments of climate-related risks. This allows insurers, reinsurers, and governments to dynamically price insurance products against extreme weather events, improving capital allocation and accessibility.

## Features
- **Quantum Amplitude Estimation** (QAE) for efficient payout distribution estimation  
- **Iterative Amplitude Estimation** for resource-optimized quantum sampling  
- **Bayesian Inference** for real-time parameter updating  
- **Hybrid Pipeline** combining quantum simulations with classical ML  
- **API-First Design** for seamless integration into existing workflows  

## Architecture
```
┌─────────────┐      ┌────────────────┐      ┌───────────────┐
│ Climate Data│ ───▶ │ Data Simulator │ ───▶ │ Quantum Engine│
└─────────────┘      └────────────────┘      └───────────────┘
                                                         │
                                                         ▼
                                                ┌────────────────┐
                                                │ Classical ML   │
                                                │ Optimizer      │
                                                └────────────────┘
                                                         │
                                                         ▼
                                                ┌────────────────┐
                                                │  Flask API     │
                                                └────────────────┘
```

## Technology Stack
- Python 3.8+  
- Qiskit & Qiskit Aer  
- SciPy, NumPy, Pandas  
- PyMC & ArviZ  
- Flask 
- D-Wave Ocean for QUBO (optional)

## Prerequisites
- Python 3.8 or higher  
- Access to a quantum simulator or QPU (optional)  
- (Optional) D-Wave Leap credentials for QUBO optimization  

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/your-org/quantum-climate-insurance-model.git
   cd quantum-climate-insurance-model
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. (Optional) Configure D-Wave credentials:
   ```bash
   export DWAVE_API_TOKEN=your_token_here
   ```

## Data Simulation
- Synthetic climate data is generated to mimic real-world temperature, precipitation, and catastrophe event distributions.
- Configurable parameters (e.g., event frequency, severity) are exposed via `simulator/config.json`.

## Quantum Pipeline
1. **Amplitude Estimation**: Constructs a quantum circuit using `RealAmplitudes` to estimate payout probabilities.  
2. **Iterative Estimation**: Optimizes circuit depth and shot budget via `IterativeAmplitudeEstimation`.  
3. **Transpilation**: Uses `qiskit.transpile` for target backend optimization.

## Classical ML Pipeline
- Fits distribution parameters (e.g., LogNormal, Gamma) using SciPy.  
- Performs Bayesian parameter updating with PyMC to incorporate new data.  
- Optimizes pricing strategy via `scipy.optimize`.

## API Endpoints
- `GET /status`: Health check  
- `POST /estimate`: Request a risk estimate (parameters in JSON)  
- `GET /results/<job_id>`: Retrieve estimation results  

## Usage Examples
```bash
# Start the API server
flask run --host=0.0.0.0 --port=5000

# Estimate risk via cURL
curl -X POST http://localhost:5000/estimate      -H "Content-Type: application/json"      -d '{
           "region": "coastal",
           "event_type": "hurricane",
           "severity": 0.8
         }'
```

## Contributing
Contributions are welcome! Please fork the repo, create a feature branch, and submit a pull request.

## License
This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

## Contact
For questions or support, please contact **Quantum HQ** at quantum-hq@example.com.
