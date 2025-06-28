# Operation BONANZA

## Overview

Operation BONANZA is a fictional law enforcement investigation designed to demonstrate how Elasticsearch can be used for criminal intelligence, digital forensics and OSINT analysis in complex organised crime cases.

**⚠️ DISCLAIMER: This is entirely fictional content created for educational and demonstration purposes only. All names, locations, and criminal activities are fabricated.**

## Purpose

This repository showcases how modern search and analytics technologies can assist law enforcement agencies in:

- **Intelligence Analysis**: Connecting disparate data points across multiple sources
- **Digital Forensics**: Analysing communications data and financial transactions

## Fictional Scenario

Operation BONANZA targets a sophisticated organised crime group involved in firearms trafficking, featuring:

- Multi-tier criminal organisation with leadership, operational, and distribution levels
- Complex money laundering operations through legitimate businesses
- International supply chains and corrupt officials
- Digital communications evidence and financial intelligence

## Repository Structure

```
operation-bonanza/
├── data/
│   ├── intel-reports/         # Criminal intelligence reports (NDJSON)
│   └── df/                   # Digital forensics extracts
│       └── messages/         # Message threads from seized devices
├── elasticsearch/
│   ├── indices/              # Index mappings and settings
│   └── pipelines/            # Ingest pipeline configurations
├── notebooks/                # Jupyter notebooks for data analysis
│   └── ingest_data_elasticsearch.ipynb  # Data ingestion tutorial
├── requirements.txt          # Python dependencies
├── pyproject.toml           # Project configuration
├── uv.lock                  # Dependency lock file
└── .env.example             # Environment variables template
```

## Key Features Demonstrated

## Sample Datasets Included

## Sample Queries

## Getting Started

### Prerequisites

- Elasticsearch 8.x deployment (Cloud or self-hosted)
- Python 3.12+ with uv package manager
- Jupyter Notebook environment

### Quick Setup

```bash
# Clone the repository
git clone https://github.com/face0b1101/operation-bonanza.git
cd operation-bonanza

# Install Python dependencies
uv sync

# Set up environment variables
cp .env.example .env
# Edit .env with your Elasticsearch credentials

# Start Jupyter and run the ingestion notebook
uv run jupyter lab
# Open notebooks/ingest_data_elasticsearch.ipynb
```

### Environment Configuration

Create a `.env` file with your Elasticsearch settings:

```env
ES_CLOUD_ID=your_cloud_id_here
ES_API_KEY=your_api_key_here
ES_CLOUD_URL=your_elasticsearch_url
```

## Use Cases Demonstrated

## Educational Value

## Technical Architecture

## Contributing

This is an educational project demonstrating Elasticsearch capabilities for law enforcement intelligence analysis. Contributions that enhance the demonstration are welcome:

- Additional realistic datasets
- New analytical queries and search patterns
- Enhanced data processing pipelines
- Documentation improvements and use case examples

Please ensure all contributions maintain the fictional nature of the dataset and follow the established data structure patterns.

## Licence

This project is licensed under the **Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International License (CC BY-NC-ND 4.0)**.

### What this means:

- ✅ **Educational Use**: Free to use for academic research, training, and educational purposes
- ✅ **Attribution Required**: Must credit the original work when used
- ❌ **No Commercial Use**: Cannot be used for commercial demos, products, or services without permission
- ❌ **No Derivatives**: Cannot modify or build upon the datasets without permission

### For Commercial Use

If you're interested in using these datasets for commercial purposes (demos, products, consulting), please raise an issue wiht your request.

[![License: CC BY-NC-ND 4.0](https://img.shields.io/badge/License-CC%20BY--NC--ND%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-nd/4.0/)

All content is fictional and created solely for educational and demonstration purposes.

## Acknowledgements

---

**Remember**: This is entirely fictional content. Any resemblance to real persons, organisations, or investigations is purely coincidental.
