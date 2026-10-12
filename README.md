# SiteMind AI

**AI Powered Intelligence for Smarter, Safer and More Sustainable Telecom Sites**

SATNAC 2026 Industry Solutions Challenge - Team Connected Minds
Topic: Intelligent Telecom: Energy, Network Security & ESG

SiteMind AI is one AI intelligence layer for every telecom site. It analyses site data every hour and combines network, energy, power, cyber, ESG and customer-experience signals (Predict -> Detect -> Analyse -> Recommend) into one site-level operational recommendation for the operator.

## Run locally
    python -m venv .venv
    .venv\Scripts\activate          (Mac/Linux: source .venv/bin/activate)
    pip install -r requirements.txt
    cd api
    uvicorn main:app --port 8000
Open http://127.0.0.1:8000 (start-up takes about 20 seconds while the models and tables load).

## Run with Docker
    docker build -t sitemind-ai .
    docker run -d --restart unless-stopped --name app -p 80:8080 sitemind-ai

## What is in the final version
- SiteMind AI branding (name, logo, slogan) and an About page explaining the architecture.
- Left menu can be hidden for a full-screen view and brought back; browser full-screen button.
- Network map can be expanded to full screen (Esc or "Back to Executive Dashboard" returns).
- Hover (desktop) or tap (phone/tablet) a site for energy, network, customer experience and cyber/physical alerts; click to pin.
- Responsive layout for phone, tablet and laptop.
- Executive Dashboard, Site Explorer, AI Recommendations, Maintenance, Simulate, Cost, Dataset, About.
- Every value is labelled Current, Predicted or Model decision.

## Layout
- `api/` FastAPI app (`main.py`, `insights.py`) and the single-page front end (`static/index.html`)
- `pipeline/` forecasting, outage, cyber, recommendation and orchestrator stages + models + serving tables
- `data/` the synthetic 60-day, 500-site dataset (720,000 hourly rows x 48 columns)
