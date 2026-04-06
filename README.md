# Interview Buddy Hub

**The Open-Source Job Hunter's Toolkit**

![Templates](https://img.shields.io/badge/templates-20-blue)
![Companies](https://img.shields.io/badge/companies-55+-green)
![Roles](https://img.shields.io/badge/roles-32-orange)
![Questions](https://img.shields.io/badge/questions-130+-purple)
![License](https://img.shields.io/badge/license-MIT-lightgrey)
![Contributors Welcome](https://img.shields.io/badge/contributors-welcome-brightgreen)

A community-driven repository of interview preparation templates, question banks, and job hunting resources. This repo serves as the content management system (CMS) for the [Interview Buddy](https://github.com/gamatech/interview-buddy) app.

## What's Inside

### Company Interview Templates (`templates/companies/`)

Detailed, company-specific interview preparation covering 55+ companies:

| Category       | Companies                                                                                  |
| -------------- | ------------------------------------------------------------------------------------------ |
| **FAANG+**     | Google, Meta, Amazon, Apple, Microsoft, Netflix                                            |
| **AI/ML**      | OpenAI, Anthropic, DeepMind, Cohere, Stability AI, Hugging Face, Mistral                   |
| **Fintech**    | Stripe, Square/Block, Plaid, Robinhood, Coinbase, Revolut                                  |
| **Enterprise** | Salesforce, Oracle, SAP, ServiceNow, Palantir, Snowflake, Databricks                       |
| **Growth**     | Uber, Airbnb, DoorDash, Instacart, Lyft, Spotify, Discord, Figma, Notion, Vercel, Supabase |
| **Infra**      | Cloudflare, Datadog, HashiCorp, Elastic, Confluent, MongoDB                                |
| **Consulting** | McKinsey, BCG, Bain                                                                        |

Each template includes:

- Realistic job descriptions
- AI interviewer instructions tailored to the company's style
- 5-8 curated questions with hints and model answers
- Interview process breakdown with timeline
- Salary ranges sourced from levels.fyi
- Company-specific tips and preparation advice

### Role Templates (`templates/roles/`)

Generic interview prep by role type:

- Behavioral (STAR Method)
- System Design Fundamentals
- Frontend Engineer
- Backend Engineer
- Product Manager

### Question Banks (`resources/question-banks/`)

- **Top 50 Behavioral Questions** with STAR framework guidance
- **Top 20 System Design Problems** with approach guides
- **15 Coding Patterns** for algorithm interviews

### Career Resources (`resources/`)

- Pre-interview checklist
- Salary negotiation playbook with scripts
- Resume optimization guide
- 35+ job boards directory

## How the App Uses This Data

The Interview Buddy app fetches JSON files directly from this repository:

```
https://raw.githubusercontent.com/gamatech/interview-buddy-hub/main/templates/index.json
```

The app reads `templates/index.json` to discover all available templates, then fetches individual template files on demand. This means:

1. **Instant updates** -- merge a PR and users see new content immediately
2. **No backend needed** -- GitHub serves as the content API
3. **Community-driven** -- anyone can contribute templates via PR

## Quick Start

### For App Users

The Interview Buddy app automatically loads templates from this repo. Just open the app and browse!

### For Contributors

1. Fork this repository
2. Add or edit a template following the schema in [CONTRIBUTING.md](CONTRIBUTING.md)
3. Validate your JSON
4. Submit a pull request

```bash
# Clone your fork
git clone https://github.com/YOUR_USERNAME/interview-buddy-hub.git
cd interview-buddy-hub

# Create a new template
cp templates/companies/google/l4-frontend.json templates/companies/your-company/your-template.json

# Edit the template with your content
# ...

# Validate JSON
node -e "JSON.parse(require('fs').readFileSync('templates/companies/your-company/your-template.json', 'utf-8'))"

# Commit and push
git add .
git commit -m "Add YourCompany senior backend template"
git push origin main
```

## Template Format

Every template follows this structure:

```json
{
  "id": "company-level-role",
  "company": "Company Name",
  "companyLogo": "https://logo.clearbit.com/company.com",
  "role": "Role Title",
  "level": "Level",
  "type": "technical",
  "difficulty": "senior",
  "jobDescription": "Detailed JD...",
  "systemPromptOverride": "AI interviewer instructions...",
  "questionBank": [
    {
      "category": "technical",
      "question": "...",
      "hints": ["...", "..."],
      "idealAnswer": "..."
    }
  ],
  "interviewProcess": {
    "rounds": 5,
    "stages": ["..."],
    "timeline": "4-6 weeks",
    "tips": ["..."]
  },
  "salaryRange": {
    "currency": "USD",
    "base": [150000, 220000],
    "totalComp": [250000, 400000],
    "source": "levels.fyi",
    "year": 2026
  },
  "tags": ["react", "typescript"],
  "contributor": "github-username",
  "updatedAt": "2026-04-06"
}
```

See [CONTRIBUTING.md](CONTRIBUTING.md) for the full specification.

## Directory Structure

```
interview-buddy-hub/
  templates/
    index.json                          # Master manifest (auto-generated)
    companies/
      google/
        l4-frontend.json
        l5-system-design.json
      meta/
        e5-fullstack.json
      amazon/
        sde2-backend.json
      ...
    roles/
      behavioral-star-method.json
      system-design-fundamentals.json
      frontend-engineer-general.json
      backend-engineer-general.json
      product-manager.json
  resources/
    question-banks/
      behavioral-top-50.json
      system-design-top-20.json
      coding-patterns.json
    checklists/
      pre-interview-checklist.json
      negotiation-playbook.json
      resume-optimization.json
    job-boards/
      aggregated-links.json
  .github/
    workflows/
      build-index.yml                   # Auto-rebuilds index on push
    PULL_REQUEST_TEMPLATE.md
  CONTRIBUTING.md
  README.md
```

## Automated Index Building

When templates are added or modified, a GitHub Action automatically rebuilds `templates/index.json` with updated counts and metadata. You don't need to update the index manually.

## Contributing

We welcome contributions from the community! Whether you want to:

- Add a template for a company not yet covered
- Update salary data or interview process information
- Add questions to existing templates
- Fix typos or incorrect information
- Add new resource files

Please read [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## Disclaimer

- Salary ranges are estimates based on publicly available data and may not reflect current offers
- Interview processes change frequently -- always verify with the company's recruiter
- Questions are representative of publicly known patterns, not actual proprietary questions
- This project is not affiliated with any of the companies listed

## License

MIT License. See [LICENSE](LICENSE) for details.

---

Built with care by the Interview Buddy community. Good luck with your interviews!
