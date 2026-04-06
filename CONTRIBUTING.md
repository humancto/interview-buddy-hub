# Contributing to Interview Buddy Hub

Thank you for considering contributing to Interview Buddy Hub! This community-driven repository powers the Interview Buddy app, helping thousands of job seekers prepare for their dream roles.

## How You Can Contribute

### 1. Add a Company Template

Company templates are the core of this project. Each template contains company-specific interview preparation materials.

**File location:** `templates/companies/{company-name}/{level}-{role}.json`

**Naming convention:**

- Company folder: lowercase, hyphenated (e.g., `google`, `square-block`)
- File name: `{level}-{role}.json` (e.g., `l4-frontend.json`, `sde2-backend.json`)

**Required fields:**

```json
{
  "id": "company-level-role",
  "company": "Company Name",
  "companyLogo": "https://logo.clearbit.com/company.com",
  "role": "Role Title",
  "level": "Level (e.g., L4, E5, Senior)",
  "type": "technical | behavioral | system-design | coding",
  "difficulty": "junior | mid | senior | expert",
  "language": "English",
  "jobDescription": "Detailed, realistic job description...",
  "systemPromptOverride": "Instructions for the AI interviewer...",
  "questionBank": [],
  "interviewProcess": {},
  "salaryRange": {},
  "tags": [],
  "contributor": "your-github-username",
  "updatedAt": "YYYY-MM-DD"
}
```

**Question bank requirements:**

- Minimum 5 questions per template
- Each question needs: category, question text, hints (array of 2-3), and idealAnswer
- Mix of categories: technical, behavioral, coding, system-design
- Questions should be commonly known, not proprietary/NDA-protected

**Salary range:**

- Source from levels.fyi, Glassdoor, or Blind
- Include base range and total compensation range
- Specify the year for the data

### 2. Add a Role Template

Role templates are generic (not company-specific) and cover a role type.

**File location:** `templates/roles/{role-name}.json`

### 3. Add Questions to a Question Bank

Contribute to the shared question banks in `resources/question-banks/`.

### 4. Add a Resource

Add checklists, guides, or job board links to `resources/`.

### 5. Fix Errors

Found incorrect salary data, outdated interview process info, or a typo? PRs welcome!

## Development Workflow

1. **Fork** the repository
2. **Create a branch**: `git checkout -b add/google-l6-ml-engineer`
3. **Add your content** following the schema above
4. **Validate your JSON**: `node -e "JSON.parse(require('fs').readFileSync('path/to/file.json', 'utf-8'))"`
5. **Submit a PR** using the provided PR template
6. **Respond to review feedback**

## Content Guidelines

### Do:

- Use publicly available information about interview processes
- Share general question types and patterns
- Provide helpful frameworks and approaches
- Include realistic salary ranges from public data sources
- Write detailed, actionable tips

### Don't:

- Share specific questions that are under NDA
- Include personally identifiable information
- Copy content from paid interview prep services
- Include offensive or discriminatory content
- Fabricate salary data or interview process details

## JSON Validation

Before submitting, validate all JSON files:

```bash
# Validate a single file
node -e "JSON.parse(require('fs').readFileSync('templates/companies/google/l4-frontend.json', 'utf-8'))"

# Validate all JSON files
find templates resources -name '*.json' -exec sh -c '
  for file; do
    node -e "JSON.parse(require(\"fs\").readFileSync(\"$file\", \"utf-8\"))" 2>/dev/null || echo "INVALID: $file"
  done
' sh {} +
```

## Code of Conduct

- Be respectful and constructive in all interactions
- Welcome newcomers and help them contribute
- Focus on the quality and accuracy of content
- Give credit where credit is due

## Questions?

Open an issue with the `question` label and we'll help you out!

## License

By contributing, you agree that your contributions will be licensed under the MIT License.
