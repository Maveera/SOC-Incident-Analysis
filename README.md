# SOC Intelligence Console

Web-based SOC assistant for incident triage, log analysis, TI enrichment, and AI-generated customer-ready draft reports.

## Live Demo

- [SOC Intelligence Console](https://maveera.github.io/SOC-Incident-Analysis/)

## Features

- **AI analysis workflow** with provider/model selection (Gemini/OpenAI and placeholders for other providers).
- **Incident rule selector** with searchable incident catalog.
- **Raw log processing** with masking/unmasking pipeline for sensitive data.
- **Threat intel enrichment** for public IPs using AbuseIPDB and VirusTotal.
- **Run validation UX** with inline status messages and disabled run button until required inputs are present.
- **Progress stepper** during execution: Masking -> TI -> AI -> Report.
- **Structured report rendering** into ordered sections:
  - Details
  - Observation
  - Impact
  - Recommended Action
  - RAW LOG
  - Classification
  - Regards
- **Copy Email Draft button** in Results section to copy customer-facing draft content.
- **Theme toggle** and improved responsive card-based layout.

## Tech Stack

- **HTML5**
- **CSS3**
- **Vanilla JavaScript (ES6+)**
- **Direct API calls** to:
  - Google Gemini API
  - OpenAI Chat Completions API
  - AbuseIPDB API
  - VirusTotal API

## Local Setup

```bash
git clone https://github.com/maveera/SOC-Incident-Analysis.git
cd SOC-Incident-Analysis
```

Run with any static host (recommended):

```bash
python -m http.server 5500
```

Then open:

- `http://localhost:5500/index.html`

## Usage

1. Enter AI key and (optionally) customer + analyst names.
2. Select incident rule, AI provider, and model.
3. Paste unmasked raw logs.
4. Click **Run Analysis Engine**.
5. Review TI + structured output in **Results**.
6. Click **Copy Email Draft** to copy the customer-ready draft.

## Notes

- For providers other than Gemini/OpenAI, backend proxy/CORS handling may be required.
- Large logs can affect model latency and token limits.
- Keep keys private; keys are stored in browser local storage for convenience.

## License

Distributed under the MIT License. See `LICENSE` for details.
