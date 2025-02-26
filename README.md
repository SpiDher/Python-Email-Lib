# Email Lib

## Overview
Email Lib is a simple Python library for sending emails using SMTP and rendering email templates with Jinja2. It provides a clean and modular way to handle email functionality in your projects.


## Features
- Dynamic email rendering using Jinja2 templates.
- Easy SMTP configuration for sending emails.
- Lightweight and reusable library.

## Installation

Install the package using pip:

```sh
pip install email_lib
```

Or install dependencies manually for local development:

```sh
pip install jinja2
```

## Usage

### Rendering an Email Template

```python
from email_lib import render_template
from jinja2 import Environment, FileSystemLoader

env = Environment(loader=FileSystemLoader("templates"))
text = render_template(env, "otp_email.txt", otp="123456", expiry=10)
print(text)
```

### Sending an Email

```python
from email_lib import send_email
import asyncio

async def main():
    success = await send_email(
        text="Your OTP code is 123456.",
        from_email="your_email@example.com",
        to_email="recipient@example.com",
        subject="🔐 Your OTP Code",
        smtp_host="smtp.example.com",
        smtp_user="your_email@example.com",
        smtp_pass="your_password"
    )
    print("Email sent successfully!" if success else "Failed to send email.")

asyncio.run(main())
```

## Configuration
Ensure you configure SMTP settings correctly before sending emails:
- **smtp_host**: Your SMTP server (e.g., `smtp.gmail.com` for Gmail).
- **smtp_user**: Your email address used for authentication.
- **smtp_pass**: Your email account password or app-specific password.

## Pypi Link
https://pypi.org/project/pyemaillib/


## Contributing
Feel free to submit pull requests or open issues for improvements.

## License
MIT License
