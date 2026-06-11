# Code of Conduct & Contributing Guidelines

## Table of Contents

* [Code of Conduct](#code-of-conduct)
* [Contributing Guidelines](#contributing-guidelines)

---

# Code of Conduct

## Our Commitment

We are committed to providing a welcoming and inclusive environment for all contributors, users, and community members of the **LLLMao** project. We believe that diversity and inclusion strengthen our community and lead to better software.

This Code of Conduct outlines our expectations for everyone participating in our community, as well as the consequences for unacceptable behavior.

---

## Our Standards

### Expected Behavior

We expect all community members to:

* **Be Respectful** — Treat all individuals with respect, regardless of background, experience level, identity, or opinions.
* **Be Inclusive** — Welcome and support newcomers, beginners, and people from underrepresented groups.
* **Be Collaborative** — Work together constructively, share knowledge, and help others succeed.
* **Be Professional** — Maintain a professional tone in all interactions.
* **Be Constructive** — Provide thoughtful feedback focused on ideas and improvements rather than personal criticism.
* **Be Patient** — Remember that everyone has different skill levels and backgrounds.
* **Be Honest** — Acknowledge mistakes gracefully and work toward solutions.

### Unacceptable Behavior

The following behaviors are not tolerated:

* Harassment or discrimination.
* Offensive or abusive language.
* Threatening or intimidating behavior.
* Spam or repetitive off-topic content.
* Trolling or intentionally disruptive conduct.
* Doxxing or sharing private information.
* Sexual harassment.
* Privacy violations.
* Submission of malicious code.
* Intellectual property violations.

---

## Scope

This Code of Conduct applies to:

* All GitHub repositories under the **Sanjay1712KSK** organization related to LLLMao.
* Issues and pull requests.
* Code reviews and comments.
* Project wikis and documentation.
* Community forums and chat channels.
* Meetups and conferences representing the project.
* Any other spaces managed by the project.

---

## Enforcement

### Reporting Violations

Report violations by:

1. **Direct Contact** – Email project maintainers.
2. **GitHub Security Advisories** – For sensitive matters.
3. **Anonymous Reporting Tools** – If available.

Please include:

* Description of the incident.
* Individuals involved.
* Time and location.
* Relevant links or context.
* Contact information (optional).

All reports are handled confidentially.

### Consequences

Violations may result in:

1. **Warning**
2. **Temporary Restriction**
3. **Permanent Ban**

Actions are proportional to the severity of the violation.

### Appeal Process

1. Submit a written appeal.
2. Explain your perspective and mitigating circumstances.
3. Accept the maintainers' final decision.

---

## Guidelines for Interactions

### For Contributors

* Review existing issues and PRs before starting.
* Use descriptive commit messages.
* Test code before submitting.
* Be open to feedback.
* Credit others' contributions.

### For Reviewers

* Focus on the code, not the person.
* Provide constructive suggestions.
* Recognize good work.
* Review promptly.
* Ask clarifying questions.

### For Maintainers

* Respond promptly.
* Provide clear guidance.
* Recognize contributor efforts.
* Lead by example.
* Be transparent.

---

## Conflict Resolution

1. Direct communication.
2. Mediation by maintainers.
3. Documentation of resolutions.
4. Follow-up to ensure effectiveness.

---

## Attribution

Adapted from:

* Contributor Covenant
* Python Community Code of Conduct
* Open-source best practices

---

## FAQ

### What if I accidentally violate the Code of Conduct?

Most violations are honest mistakes. Acknowledge the issue, apologize, and improve.

### Can the Code of Conduct change?

Yes. Updates will be communicated clearly.

### How is this different from GitHub's Community Guidelines?

This Code of Conduct is specific to the LLLMao community and complements GitHub's policies.

### What if I'm unsure about something?

Ask the maintainers or community members.

---

## Recognition

Thank you to everyone who helps make LLLMao an inclusive and productive community.

---

# Contributing Guidelines

Welcome to **LLLMao**! We're excited to have you contribute to our lightweight ChatGPT-style local AI assistant project.

---

## Quick Start

### Prerequisites

* Python 3.8+
* Node.js 14+
* Git
* Ollama
* Docker (optional)

---

## Getting Started

### 1. Fork the Repository

Click the **Fork** button on GitHub.

### 2. Clone Your Fork

```bash
git clone https://github.com/YOUR_USERNAME/LLLMao.git
cd LLLMao
```

### 3. Create a Feature Branch

```bash
git checkout -b feature/your-feature-name
```

### 4. Set Up Development Environment

See the sections below.

---

## Development Setup

### Backend (Python)

#### Create a Virtual Environment

```bash
python -m venv venv
```

#### Activate It

**Windows**

```bash
venv\Scripts\activate
```

**macOS/Linux**

```bash
source venv/bin/activate
```

#### Install Dependencies

```bash
pip install -r requirements.txt
pip install -r requirements-dev.txt
```

---

### Frontend (TypeScript/JavaScript)

```bash
cd frontend

npm install

npm install --save-dev

npm run dev
```

---

### Docker Setup

```bash
docker-compose -f docker-compose.dev.yml build

docker-compose -f docker-compose.dev.yml up
```

---

## Types of Contributions

### Bug Reports & Fixes

* Report bugs with details.
* Submit fixes with tests.

### Feature Development

* Add new features.
* Improve RAG capabilities.
* Enhance indexing functionality.

### Performance Improvements

* Optimize CPU and memory usage.
* Improve response times.

### Documentation

* Improve README files.
* Add tutorials and examples.

### Testing

* Write unit tests.
* Add integration tests.
* Improve coverage.

### Community Support

* Answer questions.
* Help other contributors.

---

## Finding Issues to Work On

Look for labels:

* `good-first-issue`
* `help-wanted`
* `enhancement`
* `bug`

Before starting:

1. Express interest.
2. Ask questions if needed.
3. Wait for maintainer feedback.
4. Ensure nobody else is working on it.

---

## Coding Standards

### Python Style

* Follow **PEP 8**.

#### Formatting

```bash
black . --line-length=100
```

#### Linting

```bash
flake8 .
```

#### Type Checking

```bash
mypy .
```

#### Example

```python
def process_documents(docs: List[str], batch_size: int = 32) -> Dict[str, Any]:
    """Process documents with RAG indexing."""
    results = {}

    for batch in chunks(docs, batch_size):
        results.update(index_batch(batch))

    return results
```

---

### TypeScript Style

Use the **Google TypeScript Style Guide**.

#### Formatting

```bash
prettier --write .
```

#### Linting

```bash
eslint .
```

#### Type Checking

```bash
tsc --noEmit
```

#### Example

```typescript
interface DocumentConfig {
  maxTokens: number;
  batchSize: number;
  indexType: 'vector' | 'semantic' | 'hybrid';
}

async function indexDocuments(
  documents: string[],
  config: DocumentConfig
): Promise<IndexResult> {
  const batches = chunk(documents, config.batchSize);
  const results: IndexResult[] = [];

  for (const batch of batches) {
    const result = await processIndexBatch(batch, config);
    results.push(result);
  }

  return mergeResults(results);
}
```

---

## Commit Guidelines

### Format

```text
<type>(<scope>): <subject>

<body>

<footer>
```

### Types

| Type     | Description             |
| -------- | ----------------------- |
| feat     | New feature             |
| fix      | Bug fix                 |
| docs     | Documentation           |
| style    | Formatting changes      |
| refactor | Refactoring             |
| perf     | Performance             |
| test     | Tests                   |
| chore    | Tooling or dependencies |

### Example

```text
feat(rag): implement hybrid search with vector and semantic matching

- Add vector similarity search
- Integrate semantic search
- Combine results with weighted ranking

Fixes #456
```

---

## Pull Request Process

### Before Creating a PR

Update your branch:

```bash
git fetch upstream
git rebase upstream/main
```

Run tests:

```bash
pytest tests/ -v

npm test
```

Check code quality:

```bash
black . && flake8 . && mypy .

prettier --check . && eslint .
```

---

## PR Template

```markdown
## Description

Brief description of changes

## Type of Change

- [ ] Bug fix
- [ ] New feature
- [ ] Breaking change
- [ ] Documentation update

## Related Issues

Fixes #(issue number)

## Testing

- [ ] Unit tests pass
- [ ] Integration tests pass
- [ ] Manual testing completed
- [ ] No regressions found

## Screenshots (if applicable)

Include before/after screenshots for UI changes

## Checklist

- [ ] Code follows style guidelines
- [ ] Self-review completed
- [ ] Documentation updated
- [ ] Tests added/updated
- [ ] All tests passing locally
```

---

## Testing

### Python

Run all tests:

```bash
pytest tests/ -v
```

Run a specific file:

```bash
pytest tests/test_rag.py -v
```

Coverage:

```bash
pytest tests/ --cov=src --cov-report=html
```

### TypeScript

Run tests:

```bash
npm test
```

Watch mode:

```bash
npm test -- --watch
```

Coverage:

```bash
npm test -- --coverage
```

---

## Test Coverage Goals

* **80%+ overall coverage**
* **100% coverage for critical functionality**
* Thorough edge-case testing

---

## Reporting Issues

### Bug Report Template

```markdown
## Description

Brief description.

## Steps to Reproduce

1. Step 1
2. Step 2
3. Step 3

## Expected Behavior

What should happen.

## Actual Behavior

What actually happened.

## Environment

- OS:
- Python Version:
- Ollama Version:
- LLLMao Version:

## Logs/Screenshots

Include relevant logs.

## Additional Context

Any additional information.
```

---

## Community and Support

### Communication Channels

* 💬 GitHub Issues
* 📝 GitHub Discussions
* 📧 Email

---

## Recognition

Contributors will be:

* Listed in `CONTRIBUTORS.md`
* Credited in releases
* Mentioned in project announcements

---

## Maintainer Review Checklist

* [ ] Code follows style guidelines.
* [ ] Tests pass.
* [ ] Documentation updated.
* [ ] Security reviewed.
* [ ] Performance impact acceptable.
* [ ] No merge conflicts.

---

## Additional Resources

* Git Documentation
* GitHub Flow Guide
* PEP 8 Style Guide
* TypeScript Handbook
* Ollama Documentation

---

## Questions?

1. Check existing issues.
2. Read the Code of Conduct.
3. Ask in GitHub Discussions.
4. Reach out to maintainers.

---

# Thank You! 🚀

Your contributions help make local AI more accessible and powerful for everyone.

---

**Last Updated:** June 2026
**Version:** 1.0
