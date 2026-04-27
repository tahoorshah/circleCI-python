# Python CI/CD Pipeline with CircleCI

Automated CI/CD pipeline for a Python project using CircleCI. Covers dependency installation, automated testing, and deployment — demonstrating cloud-native continuous integration for Python applications.

---

## 🛠️ Tech Stack

- **CircleCI** — cloud-based CI/CD platform
- **Python** — application and scripting language
- **pip** — dependency management
- **pytest** — automated testing framework

---

## 🏗️ Pipeline Overview

```
GitHub Push → CircleCI Trigger
    → Install Dependencies
    → Run Tests (pytest)
    → Build Artifact
    → Deploy
```

---

## 📁 Project Structure

```
circleCI-python/
├── .circleci/
│   └── config.yml          # CircleCI pipeline configuration
├── app.py                  # Python application
├── test_app.py             # Automated tests
└── requirements.txt        # Python dependencies
```

---

## ⚙️ CircleCI Config Overview

```yaml
version: 2.1
jobs:
  build-and-test:
    docker:
      - image: cimg/python:3.11
    steps:
      - checkout
      - run: pip install -r requirements.txt
      - run: pytest test_app.py
workflows:
  main:
    jobs:
      - build-and-test
```

---

## 🚀 Getting Started

### Prerequisites
- CircleCI account connected to your GitHub
- Repository added to CircleCI dashboard

### Local Run

```bash
# Install dependencies
pip install -r requirements.txt

# Run tests
pytest test_app.py

# Run application
python app.py
```

### CI/CD Run
Push to `main` branch — CircleCI picks it up automatically via GitHub integration.

---

## 💡 Key Concepts Demonstrated

- **Cloud CI/CD** — pipeline runs on CircleCI's managed infrastructure, no server setup required
- **Automated testing** — every push triggers test suite, catching bugs before deployment
- **Pipeline as Code** — `config.yml` defines the entire workflow, version controlled with the app
- **Docker executor** — pipeline runs inside a clean Python Docker container each time
- **Dependency caching** — pip packages cached between runs for faster builds

---

## 🔗 Related Projects

- [Terraform-CI-CD](https://github.com/tahoorshah/Terraform-CI-CD) — Terraform pipeline with GitHub Actions
- [jenkins-docker](https://github.com/tahoorshah/jenkins-docker) — Jenkins + Docker CI/CD pipeline

---

## 📝 Author

**Syed Tahoor Ali Shah**
- GitHub: [@tahoorshah](https://github.com/tahoorshah)
- Medium: [@tahoorshah](https://medium.com/@tahoorshah)
- LinkedIn: [syedtahooralishah](https://linkedin.com/in/syedtahooralishah)
