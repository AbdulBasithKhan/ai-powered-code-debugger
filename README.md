# AI-Powered Code Debugger

Welcome to the **AI-Powered Code Debugger**, a cutting-edge tool designed to detect and fix bugs in your code using advanced machine learning and AI technologies. Developed as part of an Intel internship project, this application leverages models like CodeBERT and the OpenAI API to provide intelligent bug detection and correction across multiple programming languages.

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Technologies Used](#Technologies-Used)
- [Installation](#installation)
- [Usage](#usage)
- [Known Limitations](#known-limitations)
- [Future Improvements](#future-improvements)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgments](#acknowledgments)
- [Contact](#contact)

## Overview
The AI-Powered Code Debugger is a web-based application that allows developers to input code in languages such as Python, Java, JavaScript, and C#. It uses a combination of a pre-trained CodeBERT model for bug detection and the OpenAI API for generating fixes. The tool provides a user-friendly interface built with Streamlit and Flask, making it accessible for both beginners and experienced developers.

## Features
- **Multi-Language Support**: Debug code in Python, Java, JavaScript, and C#.
- **Bug Detection**: Identifies syntax errors, logical errors, runtime errors, and type errors with confidence scores.
- **Automated Fixes**: Suggests corrections using AI, with fallback mechanisms for API limitations.
- **Code Formatting**: Professionally formats code while preserving functionality.
- **Code Explanation**: Provides simple explanations of code and detected bugs.
- **History Tracking**: Stores debugging history for review.
- **Dark Mode**: User-friendly dark mode toggle for better visibility.
- **Responsive Design**: Optimized for desktop and mobile devices.

## 🛠️ Technologies Used

- **Frontend**: Streamlit, HTML, CSS, JavaScript
- **Backend**: Flask, Celery
- **AI Models**: CodeBERT (Hugging Face), GPT-3.5 (OpenAI)
- **Database**: MongoDB (PyMongo)
- **Caching/Queue**: Redis
- **Others**: Pyperclip, Flask-CORS, Flask-Talisman, Flask-Limiter

## Installation

### Prerequisites
- Python 3.11 or later
- Git (optional, for cloning the repository)

### Steps
1. **Clone the Repository** (if using Git):
   ```bash
   git clone https://github.com/AbdulBasithKhan/ai-powered-code-debugger.git
   cd ai-powered-code-debugger

2. Create and Configure the .env File
    Create a .env file in the root directory with the following content:
    OPENAI_API_KEY=your_openai_api_key_here
    FLASK_SECRET_KEY=your_secret_key_here
    PORT=5000
    FLASK_DEBUG=true

Replace your_openai_api_key_here with your actual OpenAI API key.
Replace your_secret_key_here with a secure random string (e.g., generated with secrets.token_hex(32)).

3. Install Dependencies
    Install the required Python packages using pip:
        pip install -r requirements.txt

4. Set Up MongoDB and Redis
    Ensure MongoDB is running locally (default port: 27017) or update the MONGO_URI in the code.
    Ensure Redis is running locally (default port: 6379) or update the CELERY_BROKER_URL and CELERY_RESULT_BACKEND in the code.

5. Run the Application
    Start the Flask backend:
        python backend.py

    Start the Streamlit frontend in a separate terminal:
        streamlit run streamlit.py

    (Optional) Run Celery worker for background tasks:
        celery -A backend worker --loglevel=info

    Run the included unit tests to verify the backend functionality:
        python backend_test.py

The application will be available at http://localhost:8501 (Streamlit) and http://localhost:5000 (Flask API).

### Usage
 - Select Language: Choose your programming language from the dropdown.
 - Enter Code: Paste your code into the text area.
 - Debug Code: Click the "Debug Code" button to analyze your code.
 - If bugs are found, the tool will highlight them, suggest fixes, and provide explanations.
 - If no bugs are detected, you'll receive a confirmation message.
 - Format Code: Use the "Format Code" button to professionally format your code.
 - Load Example: Click "Load Example" to insert sample code with intentional bugs.
 - Clear Code: Use the "Clear Code" button to reset the input.
 - Toggle Dark Mode: Switch between light and dark themes using the toggle.

### Known Limitations
1. OpenAI Rate Limits: The application may fail to generate fixes if the OpenAI API rate limit is exceeded (HTTP 429). A fallback mechanism provides basic fixes in such cases.
2. Model Training: The CodeBERT model is not fully trained for all bug types, leading to lower confidence in some detections.
3. Local Development Server: The Flask development server may encounter stability issues (e.g., socket errors) on Windows; use gunicorn for production-like testing.
4. Large Code Processing: Very large code snippets (>1000 characters) are processed in the background, which may introduce delays

### Future Improvements
1. Train the CodeBERT model on a larger dataset for improved bug detection accuracy.
2. Implement a local fallback AI model to reduce dependency on the OpenAI API.
3. Add support for additional programming languages (e.g., C++, Go).
4. Enhance the UI with real-time code editing and syntax highlighting.
5. Integrate unit testing feedback into the debugging process.
6. Deploy the application on a cloud platform (e.g., Heroku, AWS) for public access.


### Contributing
Contributions are welcome! Please fork the repository and submit a pull request with your changes. Ensure you:
 - Follow the existing code style.
 - Write tests for new features.
 - Update the documentation as needed.

### License
  - This project is licensed under the MIT License. See the  file for details.

### Acknowledgments
 - Streamlit for the interactive UI.
 - Hugging Face Transformers for CodeBERT.
 - OpenAI for AI-powered code fixes and explanations.
 - MongoDB and Redis for data management.

### Contact
ContactFor questions or support, please open an issue on the GitHub repository or contact "basithkhanms@example.com".
