🛡️ YAML Cheat Sheet for DevSecOps & Security Researchers
📌 Purpose
YAML (YAML Ain’t Markup Language) is a human-readable data serialization format used for configuration files, infrastructure-as-code, and secure artifact modeling.

🔧 Syntax Essentials
Element
Example
Notes
Key-Value
env: production
Basic mapping
Nested
database:\n host: localhost
Indentation defines structure
List
- item1\n- item2
Dash prefix for sequences
Comments
# This is a comment
Use for annotation & teachback


📦 Data Types
string: "hello"
integer: 42
float: 3.14
boolean: true
null_value: null
list:
  - apples
  - oranges
map:
  key1: value1
  key2: value2

Use case: Config modeling, scan metadata, and artifact generation.

🔐 Security Hygiene
Avoid tabs: Use spaces only (typically 2 or 4).
Quote strings with special characters: "password: $ecret!"
Validate YAML before deployment using tools like yamllint, pre-commit, or CI checks.
Use anchors & aliases to reduce duplication and enforce consistency:
defaults: &defaults
  retries: 3
  timeout: 30

prod:
  <<: *defaults
  env: production


🔄 Common Patterns
✅ Environment Config
env: production
debug: false
logging:
  level: info
  output: stdout

✅ CI/CD Pipeline
jobs:
  build:
    steps:
      - run: echo "Building..."
      - run: make test

✅ Secrets & Vaults
secrets:
  api_key: ${API_KEY}
  db_password: ${DB_PASS}

Use case: Secure injection via environment variables or secret managers.

🧠 Annotated Rituals
Daily Ops: yamllint ., pre-commit run --all-files
Outreach Artifact: echo "Scan complete: $(date)" >> scan.yaml
Teachback Loop: cat config.yaml | grep 'timeout'

✅ Formatting Tips
Use consistent indentation (2 or 4 spaces).
Use quotes for strings with special characters or leading numbers.
Use comments to annotate intent and teachback logic.
Avoid inline complexity—prefer nested clarity.
