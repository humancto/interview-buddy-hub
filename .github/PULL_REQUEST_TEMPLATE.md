## What type of contribution is this?

- [ ] New company template
- [ ] New role template
- [ ] New question bank / resource
- [ ] Update to existing template
- [ ] Bug fix (incorrect data, broken JSON)
- [ ] Other (describe below)

## Description

<!-- Briefly describe your contribution. What company/role does it cover? What's included? -->

## Checklist

### For template contributions:

- [ ] JSON is valid (run `node -e "JSON.parse(require('fs').readFileSync('path/to/file.json', 'utf-8'))"`)
- [ ] Follows the template schema (see CONTRIBUTING.md)
- [ ] Includes at least 5 questions in the question bank
- [ ] Job description is realistic and detailed
- [ ] Salary ranges are sourced from levels.fyi or similar
- [ ] Interview process information is accurate and current
- [ ] Tags are relevant and use lowercase-kebab-case
- [ ] `updatedAt` field is set to today's date

### For question bank contributions:

- [ ] Questions are original or commonly known interview questions
- [ ] Hints and ideal answers provide genuine value
- [ ] Questions are categorized correctly (behavioral, technical, coding, system-design)

### General:

- [ ] No personally identifiable information (PII) is included
- [ ] No proprietary or confidential interview questions from specific companies
- [ ] Content is respectful and professional
- [ ] I have tested that the JSON parses correctly

## Source / How do you know this information?

<!-- How did you gather this information? Personal experience, public data, etc. -->
<!-- Note: Do not share NDA-protected interview content -->

## Related Issues

<!-- Link any related issues: Fixes #123, Closes #456 -->
