# Q-SENTINEL

**AI-Driven Correlation of Cybersecurity Telemetry & Transactional Behaviour — with Quantum-Risk Awareness**

Built for **Finspark Hackathon 2026** (Bank of Maharashtra) by **Team Quantums**

🔗 **Live prototype:** `https://niharikasingh09.github.io/Q-Sentinel/`
🎥 **Demo video:** https://drive.google.com/file/d/1mHcpgtT9RvpUy0gjsJ60eM2NXBmEsJdO/view?usp=sharing
📊 **Slide deck:** [`Q-Sentinel_Finspark_Hackathon.pptx`](Q-Sentinel_Finspark_Hackathon.pptx)

---

## The Problem

Banks run two parallel universes of data — cybersecurity telemetry (logins, device fingerprints, network traffic) and transactional behaviour (payments, transfers, account activity) — that almost never talk to each other. This blind spot lets sophisticated attacks slip through, including emerging quantum threats like **Harvest-Now-Decrypt-Later (HNDL)**, where adversaries exfiltrate encrypted data today to decrypt once quantum computers mature.

## What Q-SENTINEL Does

- **Correlates** cybersecurity telemetry with transactional behaviour on a single identity graph
- **Detects** cyber threats and fraud patterns proactively, instead of scoring them in separate silos
- **Scores quantum-risk exposure** on every transaction channel, flagging legacy/weak encryption against NIST post-quantum cryptography (PQC) guidance
- **Reduces false positives** by requiring joint evidence across both streams before an alert fires
- **Explains every alert** in plain language (SHAP-style factor breakdown), so analysts and auditors aren't handed a black box

## Architecture

```
Data Sources ─▶ Ingestion & Identity Graph ─▶ Correlation Engine ─▶ Explainability Layer ─▶ Analyst Dashboard
(telemetry +      (Kafka + entity              (graph + anomaly        (SHAP reasoning)       (ranked, actionable
 transactions)      resolution)                   models)                                        alerts)
                                                       ▲
                                              Quantum-Risk Module
                                          (PQC exposure scoring — NIST
                                             Kyber / Dilithium)
```

Full diagram: see the deck in `docs/`.

## Repo Contents

| Path | Description |
|---|---|
| `index.html` | Working prototype — a simulated live analyst console (open directly in any browser, or view via GitHub Pages) |
| `Q-Sentinel_Finspark_Hackathon.pptx` | Full hackathon submission deck |

## Running the Prototype Locally

No build step, no dependencies. Just open the file:

```bash
git clone https://github.com/niharikasingh09/Q-Sentinel.git
cd Q-Sentinel
open index.html   # or just double-click it
```

The console auto-generates simulated alerts, telemetry/transaction anomaly scores, and quantum-risk scores every few seconds so it demonstrates the full flow without any setup. **All data shown is synthetically generated in-browser for demonstration purposes — no real bank data is used, and there is no backend or trained model behind this prototype yet.**

## Tech Stack (Planned Full Build)

- **AI/ML:** Python, Scikit-learn, XGBoost, PyTorch, SHAP
- **Correlation Engine:** Neo4j / NetworkX identity graph
- **Streaming & Storage:** Apache Kafka, Spark Structured Streaming, PostgreSQL, Elasticsearch
- **Quantum Risk Reference:** NIST Post-Quantum Cryptography standards (Kyber, Dilithium), MITRE ATT&CK
- **Dashboard:** React/Next.js analyst console
- **Deployment:** Docker, Kubernetes, MLflow

## Judging Criteria Coverage

| Criterion | Weight | Where to look |
|---|---|---|
| Business Potential & Relevance | 40% | Deck, Slide 8 |
| Security Considerations | 30% | Deck, Slide 13 |
| Uniqueness of Approach | 15% | Deck, Slide 9 |
| User Experience | 5% | Prototype + Deck, Slide 10 |
| Scalability | 5% | Deck, Slide 11 |
| Ease of Deployment & Maintenance | 5% | Deck, Slide 12 |

## Team

**Quantums**
- Niharika Singh — B.Tech Final Year, Banasthali Vidyapith

## License

MIT — see [`LICENSE`](LICENSE)
