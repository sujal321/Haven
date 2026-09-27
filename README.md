🏠 Haven

Privacy-First Wellbeing Support & Human-Centred Early Intervention

«Haven is a consent-first digital wellbeing platform designed to help people understand changes in their personal wellbeing patterns and connect meaningful signals with human counsellor support.»

🔗 Live Demo: https://tiny-scone-ed6619.netlify.app/

---

✨ Overview

Haven is designed around one principle:

«Your wellbeing data should remain under your control.»

The platform provides a private space where users can voluntarily complete wellbeing check-ins, review personal trajectories, manage data-sharing consent, and—where appropriate—surface explainable signals for human counsellor review.

Haven is not a diagnostic system. Its purpose is to support early awareness and human intervention rather than replace professional judgement.

---

🎯 Problem

People often experience gradual changes in:

- Mood
- Daily wellbeing
- Sleep and activity patterns
- Communication behaviour
- Check-in consistency

These changes can be difficult to recognize when viewed individually.

At the same time, existing digital wellbeing systems can create concerns around:

- Privacy
- Continuous monitoring
- Unclear consent
- Black-box risk scores
- Excessive data collection
- Lack of human oversight

Haven approaches the problem through explicit consent, personal baselines, explainable signals and human-in-the-loop support.

---

💡 Solution

Haven connects four major stages:

        USER CONSENT
              │
              ▼
       VOLUNTARY CHECK-IN
              │
              ▼
      PERSONAL TRAJECTORY
              │
              ▼
     EXPLAINABLE SIGNALS
              │
              ▼
       HUMAN REVIEW
              │
              ▼
       SUPPORT / ACTION

The system is designed so that an automated signal is not treated as a diagnosis.

---

🚀 Current Features

👤 User Experience

📝 Daily Check-in

Users can record how they are feeling through a simple check-in experience.

The interface supports:

- Mood selection
- Optional personal notes
- Check-in history
- Personal trajectory
- Wellbeing signal visualization

---

📈 Personal Trajectory

Haven presents changes relative to the user's personal pattern rather than relying only on population-level thresholds.

Example:

Personal Baseline
       │
       ├── Normal variation
       │
       ├── Emerging change
       │
       └── Elevated signal

This makes the experience more contextual and easier to understand.

---

🔐 Consent Management

Consent is treated as a first-class feature.

Users can independently manage:

- Text check-ins
- Voice processing
- Wearable signals

They can also:

- Revoke individual consent
- Revoke all consent
- Delete demo data
- Review privacy activity

---

🎙️ Voice Processing Concept

Haven's architecture supports a future bounded voice-processing workflow:

User consent
     ↓
Short voice interaction
     ↓
Feature extraction
     ↓
Inference
     ↓
Derived signal
     ↓
Raw audio discarded

The current Netlify demo uses simulated processing and does not capture or upload real audio.

---

👨‍⚕️ Counsellor Workspace

The counsellor interface provides a human-in-the-loop workflow.

It is designed around:

Case Queue

Case
 ↓
Signal
 ↓
Evidence
 ↓
Trend
 ↓
Human Review

Counsellors can view:

- Case status
- Signal level
- Evidence count
- Recent trend
- Review state
- Acknowledgement workflow

The intention is to provide evidence for human review, rather than automated clinical decisions.

---

🧠 Explainable Signals

Instead of presenting only:

Risk = 82%

Haven is designed to communicate:

Why was this surfaced?

• Recent trajectory changed
• Multiple signals contributed
• Change differs from personal baseline
• Human review recommended

This improves transparency and reduces the opacity associated with black-box outputs.

---

🏗️ Architecture

Current Prototype Architecture

┌───────────────────────────────┐
│          Haven Web UI         │
│                               │
│  Dashboard                    │
│  Check-in                     │
│  Trajectory                   │
│  Privacy                      │
│  Counsellor Workspace         │
└───────────────┬───────────────┘
                │
                ▼
       Browser Local State
                │
                ▼
        Demo Signal Layer

The current Netlify deployment is intentionally zero-build and backend-independent.

---

🔮 Production Architecture

The intended production architecture is:

┌──────────────────────────────┐
│        Haven Android         │
│                              │
│ Jetpack Compose              │
│ ViewModels                   │
│ Local Privacy Layer          │
└──────────────┬───────────────┘
               │
               ▼
       Consent Gateway
               │
               ▼
       Secure API Layer
               │
        ┌──────┴──────┐
        ▼             ▼
     FastAPI        WebSocket
        │             │
        ▼             ▼
 PostgreSQL/       Real-time
 TimescaleDB       Events
        │
        ▼
   Signal Engine
        │
        ▼
   ML Inference
        │
        ▼
 Explainable Risk
        │
        ▼
 Counsellor Portal

---

🧩 Planned Production Components

Mobile

- Kotlin
- Jetpack Compose
- MVVM
- StateFlow
- Room
- Android Keystore
- Health Connect
- On-device signal processing

Backend

- Python
- FastAPI
- PostgreSQL
- TimescaleDB
- Redis
- WebSockets
- Celery

Machine Learning

Potential pipeline:

Text
 │
 ├── NLP features
 │
 └── Emotion / sentiment features
          │
Voice ────┤
 │        │
 ├── Prosody
 ├── Pitch
 ├── Speech rate
 └── Pause statistics
          │
Wearable ┤
 │
 ├── Sleep
 ├── Activity
 ├── HR
 └── HRV
          │
          ▼
   Personal Baseline
          │
          ▼
   Multimodal Features
          │
          ▼
    Risk / Signal Model
          │
          ▼
 Explainable Output

---

🔒 Privacy by Design

Haven follows a privacy-first architecture.

Principles

1. Explicit consent

Data modalities should never be silently enabled.

2. Data minimization

Only required information should be processed.

3. Human oversight

Automated signals should support—not replace—human judgement.

4. Explainability

Users and counsellors should understand why a signal was generated.

5. Local processing where practical

Sensitive feature extraction should happen on-device where technically feasible.

6. No unnecessary raw-data retention

The production design should avoid storing raw voice recordings when derived features are sufficient.

7. Revocation

Users should be able to revoke consent.

8. Deletion

Users should be able to request deletion of their data.

---

⚠️ Important Safety Boundary

Haven is not a medical diagnostic system.

The following concepts must remain separate:

Signal
  ≠
Clinical diagnosis

Anomaly
  ≠
Confirmed crisis

Missing data
  ≠
Mental-health deterioration

The system should provide an insufficient-data state instead of making unsupported conclusions.

Emergency situations should use appropriate emergency or professional support channels rather than relying on automated inference.

---

🌐 Live Demo

Haven Web App

🔗 https://tiny-scone-ed6619.netlify.app/

The demo currently provides:

- Dashboard
- Check-ins
- Trajectory
- Consent management
- Privacy ledger
- Counsellor workspace
- Explainable alerts
- Simulated voice workflow

---

🛠️ Running Locally

No package installation is required for the current web prototype.

Clone the repository:

git clone https://github.com/YOUR_USERNAME/Haven.git
cd Haven

Open:

index.html

Or use a local server:

python -m http.server 8000

Then visit:

http://localhost:8000

---

☁️ Netlify Deployment

Haven is configured for zero-build Netlify deployment.

Build settings

Build command:
None

Publish directory:
.

The repository includes:

netlify.toml
_headers
index.html

These configure the deployment and security headers.

---

📁 Project Structure

Haven/
│
├── index.html
│
├── netlify.toml
│
├── _headers
│
├── README.md
│
└── docs/
    ├── architecture.md
    ├── privacy.md
    ├── security.md
    └── roadmap.md

---

🗺️ Development Roadmap

Phase 1 — Prototype

- [x] Responsive web UI
- [x] Dashboard
- [x] Check-in
- [x] Trajectory
- [x] Privacy controls
- [x] Counsellor workspace
- [x] Explainable alert interface
- [x] Netlify deployment

Phase 2 — Backend

- [ ] FastAPI API
- [ ] PostgreSQL
- [ ] Authentication
- [ ] RBAC
- [ ] Consent service
- [ ] Audit service
- [ ] Secure API communication

Phase 3 — Mobile

- [ ] Android application
- [ ] Encrypted local storage
- [ ] Health Connect integration
- [ ] Offline-first synchronization
- [ ] Secure authentication

Phase 4 — Intelligence

- [ ] Personal baseline engine
- [ ] NLP pipeline
- [ ] Voice feature extraction
- [ ] Multimodal fusion
- [ ] Model evaluation
- [ ] Calibration
- [ ] Explainability

Phase 5 — Production

- [ ] Security audit
- [ ] Threat modelling
- [ ] Privacy review
- [ ] Automated testing
- [ ] CI/CD
- [ ] Observability
- [ ] Production deployment

---

🧪 Testing Strategy

Production testing should cover:

Unit Tests
     ↓
Integration Tests
     ↓
API Tests
     ↓
UI Tests
     ↓
Security Tests
     ↓
ML Evaluation
     ↓
End-to-End Tests

Important test cases include:

- Consent revoked → modality cannot be processed
- User deletes data → data is removed
- Unauthorized counsellor → case access denied
- Expired authentication → API rejects request
- Missing signals → insufficient-data state
- Model uncertainty → uncertainty communicated
- Network unavailable → graceful offline behaviour

---

📊 Project Status

Component| Status
Haven Web UI| ✅ Working
Netlify Deployment| ✅ Live
Responsive Design| ✅
Check-in Flow| ✅
Privacy UI| ✅
Counsellor UI| ✅
Explainable Alert UI| ✅
Backend| 🔄 Planned
Authentication| 🔄 Planned
Real ML| 🔄 Planned
Real Voice Processing| 🔄 Planned
Wearable Integration| 🔄 Planned
Production Security| 🔄 Planned

---

👥 Team

Project: Haven

Domain: Digital Wellbeing / Human-Centred Technology

Development: TechTitans

---

📜 License

This project is currently intended for educational, research and hackathon demonstration purposes.

Before production deployment, licensing, privacy, security, clinical-safety and regulatory requirements should be reviewed independently.

---

⭐ Vision

Haven aims to make digital wellbeing technology feel less like surveillance and more like a private space for awareness, consent and human support.

Private by design.
Human at the centre.
Evidence over assumptions.
