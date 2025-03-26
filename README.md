# Resume Screening and Email Notification System

## Overview
This project automates the process of screening resumes and sending email notifications to candidates. It extracts relevant skills from resumes and matches them against predefined skill sets. If a candidate qualifies, they receive an interview call email; otherwise, they are sent a rejection email.

## Features
- Extracts candidate details (name, email, skills) from resumes.
- Matches extracted skills against predefined job requirements.
- Sends interview or rejection emails based on skill matching.
- Uses Gmail SMTP for sending emails.
- Implements OAuth2 authentication for secure email sending.

## Installation
### Prerequisites
Ensure you have Python installed along with the following dependencies:
```sh
pip install nltk smtplib pyresparser google-auth google-auth-oauthlib google-auth-httplib2 google-auth-oauthlib google-auth google-api-python-client
```
Additionally, download the required NLTK data:
```python
import nltk
nltk.download('stopwords')
```

## Configuration
1. **Google API Credentials:**
   - Obtain Gmail API credentials by creating a project in the [Google Developer Console](https://console.developers.google.com/).
   - Download the `client_secret.json` file and save it in your project directory.
   - Authenticate the application by running the script; it will generate `token.json`.

2. **SMTP Configuration:**
   - Ensure that your Gmail account allows [Less Secure Apps](https://myaccount.google.com/security) or set up an App Password.
   - Modify the `smtplib.SMTP` settings accordingly.

3. **Resume File Path:**
   - Update the path in `ResumeParser` to point to the correct resume file location.

## Usage
1. **Run the Script:**
   ```sh
   python script.py
   ```
2. The script will:
   - Parse the resume for skills.
   - Compare skills with predefined job role requirements.
   - Send an interview email if the candidate qualifies.
   - Send a rejection email if they do not qualify.

## File Structure
```
|-- script.py           # Main script for resume processing and email sending
|-- token.json          # Stores authentication tokens (auto-generated)
|-- client_secret.json  # Google API credentials
|-- sample_resume.pdf   # Example resume for testing
```

## Future Enhancements
- Extend skill-matching to multiple job roles.
- Implement a web-based interface for uploading resumes.
- Store and analyze candidate data using a database.
