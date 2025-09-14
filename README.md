# 📝 Python Logging Notes

This repository contains concise and practical notes on **Python Logging**.  
It covers **basics, best practices, and real-world examples** to help developers use logging effectively in Python projects.

---

## 📌 Why Logging?
- Provides better visibility into application behavior than `print()`.
- Helps in debugging, monitoring, and auditing.
- Supports multiple logging levels (INFO, DEBUG, WARNING, ERROR, CRITICAL).
- Can log to console, files, or external systems.

---

## 🚀 Getting Started

### Basic Example
```python
import logging

# Configure logging
logging.basicConfig(level=logging.INFO)

logging.info("This is an info message")
logging.warning("This is a warning")
logging.error("This is an error")

### ⚡ Best Practices

## Use module-level loggers

import logging
logger = logging.getLogger(__name__)


# Avoid print() for debugging
# Use appropriate logging levels instead.

## Use basicConfig or dictConfig for project-wide setup

logging.basicConfig(
    level=logging.DEBUG,
    format="%(asctime)s - %(name)s - %(levelname)s - %(message)s",
    handlers=[
        logging.FileHandler("app.log"),
        logging.StreamHandler()
    ]
)


## Log Exceptions with exc_info=True

try:
    1 / 0
except ZeroDivisionError:
    logger.exception("Division by zero error")


## Use different log levels properly

DEBUG → Detailed diagnostic info

INFO → General application flow

WARNING → Something unexpected but still running

ERROR → A failure in part of the system

CRITICAL → Application crash or serious issue

### 📂 Project Logging Example
project/
│── app.py
│── user_service.py
│── logging.conf


user_service.py

import logging
logger = logging.getLogger(__name__)

def create_user(username):
    logger.info("Creating user: %s", username)
    return {"user": username}

### 🔧 Advanced Topics

## Logging to multiple files.

Rotating log files (RotatingFileHandler, TimedRotatingFileHandler).

JSON structured logging.

Logging in Django/Flask applications.

Integration with monitoring tools (ELK, Datadog, AWS CloudWatch).

📖 References

Python Logging Documentation

Logging Cookbook

👨‍💻 Author

Created with ❤️ by Onkar Ambuse
For interview prep & real-world Python projects.


---

Would you like me to make this **short and crisp (1-page quick reference)** or **detailed (like a mini-guide with full explanations)**?
