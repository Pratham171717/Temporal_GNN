# Contributing to Temporal GNN AML Forensics

Thank you for your interest in contributing to this project!

## Development Setup

1. **Fork and clone** the repository:
   ```bash
   git clone https://github.com/Pratham171717/<repo-name>.git
   cd <repo-name>
   ```

2. **Set up Python environment** (Python 3.11 recommended):
   ```powershell
   py -3.11 -m venv .venv
   .\.venv\Scripts\activate
   pip install torch==2.10.0 --index-url https://download.pytorch.org/whl/cpu
   pip install -r requirements.txt
   pip install -r requirements_ui.txt
   ```

3. **Verify Artifacts**:
   ```powershell
   python verify_artifacts.py
   ```

4. **Launch Application**:
   ```powershell
   streamlit run app.py
   ```

## Guidelines

- **Code Style**: Follow PEP 8 guidelines for Python code.
- **Reproducibility**: Ensure model evaluation assertions and artifact verification passes before submitting pull requests.
- **Pull Requests**: Provide clear descriptions of changes, test coverage, and rationale.
