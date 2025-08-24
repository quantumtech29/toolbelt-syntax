🛡️ Python Cheat Sheet for DevSecOps & Security Researchers
📌 Purpose
Optimized for secure scripting, automation, artifact generation, and threat modeling across CI/CD pipelines and forensic workflows.

🔧 Script Anatomy
Component
Example
Notes
Shebang
#!/usr/bin/env python3
Ensures portability
Imports
import os, sys, logging
Standard modules
Entry Point
if __name__ == "__main__":
Prevents auto-execution on import
Comments
# single, """multi-line"""
Use for annotation & teachback


📦 Variables & Data Types
x = 42              # Integer
pi = 3.14           # Float
name = "Rashard"    # String
is_secure = True    # Boolean
data = [1, 2, 3]    # List
config = {"env": "prod"}  # Dict

Use case: Artifact modeling, config parsing, and telemetry.

🔐 Security Hygiene
import os
try:
    with open("config.yaml") as f:
        config = f.read()
except FileNotFoundError:
    logging.error("Missing config file")

Use case: Secure file handling, audit trail, and exception logging.

🔄 Control Structures
if user != os.getlogin():
    print("User mismatch")

for i in range(3):
    print(i)

while True:
    break

match status:
    case 200: print("OK")
    case 403: print("Forbidden")


🧪 Functions & Return Values
def add(x, y):
    return x + y

def scan_report():
    return {"status": "complete", "timestamp": time.time()}

Use case: Modular tooling, teachback loops, and artifact generation.

📤 Logging & Error Handling
import logging
logging.basicConfig(level=logging.INFO)
logging.info("Scan started")

Use case: CI/CD observability, forensic traceability, and outreach artifacts.

🧰 Built-ins & Utilities
len(data)           # Length
type(config)        # Type check
sum([1, 2, 3])      # Aggregation
sorted(data)        # Sort

Use case: Data validation, telemetry parsing, and artifact prep.

🔄 File & OS Ops
os.listdir(".")             # List files
os.remove("temp.txt")       # Delete file
os.system("ls -la")         # Shell command

Use case: Secure teardown, log rotation, and system introspection.

🌐 Web & API Ops
import requests
r = requests.get("https://api.example.com")
print(r.status_code)

Use case: Threat modeling, telemetry ingestion, and outreach endpoints.

🧠 Annotated Rituals
Daily Ops: black ., pytest, bandit -r .
Outreach Artifact: print(f"Scan complete: {datetime.now()}")
Teachback Loop: help(str.replace)

✅ Formatting Tips
Use code blocks for clarity.
Use tables for quick comparisons.
Use emoji headers to segment rituals and modules.
Annotate with intent and use case to make it reproducible.
