# AI-RadioGuard

**AI-Driven Radio Spectrum Management & Illegal Transmission Detector**

AI-RadioGuard is an open-source platform that leverages Software-Defined Radio (SDR) hardware and modern machine learning models to continuously monitor the radio spectrum, classify signals, and automatically detect potential violations such as unlicensed transmissions, interference sources, or out-of-band operations.

Inspired by Japan's sophisticated **DEURAS (Detect Unlicensed Radio Stations)** system operated by the Ministry of Internal Affairs and Communications (MIC), this project brings advanced, accessible radio monitoring capabilities to researchers, radio enthusiasts, community networks, regulatory bodies, and security teams worldwide. [[14]](grokcitation://citation?card_id=1b9fbd&card_type=citation_card&type=render_inline_citation&citation_id=14)

## Goals
- Promote responsible and legal radio usage
- Provide early warning for harmful interference
- Democratize professional-grade spectrum monitoring tools
- Support education and research in RF (Radio Frequency) AI applications

## Key Features

- **Real-time Spectrum Monitoring** — Wideband scanning using affordable SDR hardware (RTL-SDR, HackRF, USRP, etc.)
- **AI Signal Classification** — Deep learning models trained to identify modulation types, protocols, and anomalous signals (AM/FM, digital modes, unknown emitters)
- **Illegal Transmission Detection** — Flags signals outside authorized bands, exceeding power limits, or matching known unlicensed patterns
- **Automated Alert System** — Generates warnings via email, Telegram, webhook, or audio broadcasts. Can integrate with direction-finding hardware for approximate localization
- **Direction Finding & Logging** — Supports multi-sensor setups for basic triangulation (similar to DEURAS sensor stations)
- **Dashboard & Visualization** — Web-based UI showing live waterfall, signal history, violation events, and heatmaps
- **Compliance Database** — Configurable rulesets for different countries/regions (pre-loaded with common regulatory bands)
- **Data Export & Forensics** — Record IQ samples and metadata for analysis or reporting

## How It Works

1. SDR hardware captures raw IQ samples across selected frequency ranges.
2. Pre-processing and feature extraction feed into lightweight CNN / Transformer models for signal classification.
3. Rule engine cross-references detections against regulatory databases.
4. Violations trigger alerts and logging.
5. Optional multi-node deployment enables distributed monitoring and basic geolocation.

The system emphasizes **non-intrusive monitoring** and is designed for legal, research, and educational use only. Users are responsible for complying with all local radio regulations.

## Use Cases
- Amateur radio clubs and community mesh networks
- University RF research labs
- Spectrum management in developing regions
- Interference troubleshooting for licensed operators
- Educational tool for learning about radio regulations and signal intelligence

## Tech Stack
- **Backend**: Python + GNU Radio / SoapySDR
- **AI/ML**: PyTorch / TensorFlow Lite (with models for low-SNR classification)
- **Frontend**: React / Streamlit / Grafana
- **Hardware Support**: RTL-SDR, HackRF One, LimeSDR, USRP, etc.
- **Deployment**: Docker + optional Kubernetes for multi-sensor setups

## Getting Started
(See `docs/` for detailed setup guides)

```bash
git clone [https://github.com/kenta181/ai-radioguard.git](https://github.com/kenta181/ai-radioguard.git)
cd ai-radioguard
docker-compose up
