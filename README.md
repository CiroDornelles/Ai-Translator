      
# AI-Powered Lore Translator

## 🧙‍♂️ Translate the Mystical Narratives, Seamlessly.

The **AI-Powered Lore Translator** is a robust, cross-platform desktop application designed to provide specialized translation of complex lore. Initially focused on the rich narratives of **White Wolf's Mage: The Ascension**, its modular architecture ensures future compatibility with other intricate fictional universes.

Our core philosophy revolves around delivering a "one-click wonder" and "plug-and-play" experience for non-technical users. It's built to be open-source, free, visually stunning, highly intuitive, and scalable for long-term growth.

---

## ✨ Features

Our translator aims to be the definitive tool for lore enthusiasts and storytellers:

*   **Intelligent AI Translation:** Powered by the cutting-edge **Gemini API** with highly customizable and context-aware prompts.
*   **Flexible Input Methods:**
    *   **Clipboard Text:** Simply copy any text, and the app is ready to translate.
    *   **_Future:_ Clipboard Image + OCR:** Extract text directly from images, scans, or PDFs using advanced OCR technology (DocLing/Tesseract).
*   **Rich HTML Output:** Generates beautifully formatted HTML output with external CSS (saved in a "Documents" folder), allowing for rich text formatting (Markdown) and explanations from the AI model.
*   **Intuitive Prompt Management:** A user-friendly GUI allows you to easily select, create (manually or via AI), edit, and save personalized translation prompts tailored to specific lore.
*   **Comprehensive Glossary & Jargon Management:** Maintain a local SQLite database of key-value lore terms and jargon. These terms can be injected directly into the AI prompt to ensure consistent and accurate translations.
*   **Collaborative Project Panel (GUI):**
    *   Load documents (text, PDF) and automatically segment them for translation.
    *   Track translation progress (translated, reviewed, pending).
    *   Maintain a detailed translation history.
    *   **_Future:_** Advanced collaborative features like task assignment, comments, and real-time synchronization.
*   **Internal REST API:** The Flutter frontend communicates seamlessly with the local Python backend via a secure, internal REST API.
*   **In-App Updates:** Notifies users of new versions via the GUI, providing a direct link to GitHub Releases for easy updating.
*   **Internationalization (i18n) by Default:** The application's user interface is designed from the ground up to support multiple languages, making it accessible to a global audience. Translations for new languages are always welcome!

---

## 💻 Technology Stack

Our chosen stack combines the best of modern development for a powerful and flexible application:

*   **Frontend (GUI): Flutter (Language: Dart)**
    *   **Justification:** Provides a fantastic UI/UX, native performance, true cross-platform capabilities (desktop, web, future mobile), and results in a reasonably sized executable.
*   **Backend (Core Logic & API): Python (with Flask/FastAPI)**
    *   **Justification:** Leverages Python's unbeatable ecosystem for AI and data processing. Existing logic (Gemini API calls, OCR processing) can be directly reused. Flask/FastAPI provides a robust local REST API for communication with Flutter.
*   **Packaging:** PyInstaller (for Python backend) + Native Installer Tools (NSIS for Windows, pkgbuild/DMG for macOS, etc. for bundling Flutter and Python together).
    *   **Justification:** Enables a unified, "one-click" installation experience for the end-user.
*   **CI/CD:** GitHub Actions
    *   **Justification:** Automates cross-platform builds and GitHub Releases on tag pushes, ensuring consistent and timely updates.
*   **Local Database:** SQLite
    *   **Justification:** Lightweight, serverless, and perfect for managing project data, glossaries, and translation history directly on the user's machine.

---

## 🚀 Installation & Setup

### For End-Users (Coming Soon!)

We are actively working on providing native installers for Windows, macOS, and Linux. Our goal is a "one-click wonder" experience where you simply download, install, and run the application. Stay tuned for official releases!

### For Developers

If you wish to contribute or run the application from source, follow these steps:

#### Prerequisites

*   **Python 3.8+:** Make sure Python is installed and added to your PATH.
*   **Flutter SDK:** Follow the official Flutter installation guide for your operating system.
*   **Git:** For cloning the repository.
*   **(Optional for OCR functionality):** Tesseract OCR (and its language data) will be required later for image-to-text translation.

#### 1. Clone the Repository

git clone https://github.com/your-username/ai-powered-lore-translator.git
cd ai-powered-lore-translator

    

IGNORE_WHEN_COPYING_START
Use code with caution. Markdown
IGNORE_WHEN_COPYING_END
2. Backend Setup (Python)

Navigate to the project root and set up the Python environment:

      
# Create a virtual environment
python3 -m venv venv
source venv/bin/activate # On Windows use `venv\Scripts\activate`

# Install backend dependencies (Flask/FastAPI, Google-Gemini, etc.)
pip install -r requirements.txt # (You'll need to create this file with your dependencies)

    

IGNORE_WHEN_COPYING_START
Use code with caution. Bash
IGNORE_WHEN_COPYING_END
3. Frontend Setup (Flutter)

Navigate to the Flutter project directory (e.g., flutter_app if you choose to separate it, or directly in root if combined):

      
# Get Flutter dependencies
flutter pub get

    

IGNORE_WHEN_COPYING_START
Use code with caution. Bash
IGNORE_WHEN_COPYING_END
4. Configure API Key

You will need a Google Gemini API Key.
Create or open config/app_config.json and add your API key:

      
{
    "api_key": "YOUR_GEMINI_API_KEY_HERE",
    "selected_prompt": "mage_crusade_prompt.txt",
    "auto_copy_to_clipboard": true
}

    

IGNORE_WHEN_COPYING_START
Use code with caution. Json
IGNORE_WHEN_COPYING_END

Important: Keep your API key secure and do not commit it directly to public repositories.
5. Running the Application (Development Mode)

You will need to run the Python backend service and the Flutter frontend application separately for development:

In Terminal 1 (for Python Backend):

      
source venv/bin/activate # Activate your Python virtual environment
python src/main_backend_api.py # Or whatever your main Flask/FastAPI entry point is called

    

IGNORE_WHEN_COPYING_START
Use code with caution. Bash
IGNORE_WHEN_COPYING_END

In Terminal 2 (for Flutter Frontend):

      
flutter run

    

IGNORE_WHEN_COPYING_START
Use code with caution. Bash
IGNORE_WHEN_COPYING_END
📖 Usage

    Launch the Application: Once installed/running, the intuitive GUI will appear.

    Configure API Key: (If not already set) Provide your Google Gemini API key in the settings.

    Select/Manage Prompts: Choose from pre-defined lore-specific prompts or create your own custom prompts via the "Prompt Management" section.

    Manage Glossary: Add or edit specific lore terms and their translations in the "Glossary" section to ensure consistency.

    Input Text: Copy the lore text you wish to translate to your clipboard.

    Translate: Click the "Translate" button. The application will send the text to the Gemini API with your chosen prompt and glossary.

    View Output: The translated content will be displayed within the app's in-app browser (or your default browser) as a formatted HTML document, including any model explanations. The HTML file will also be saved locally.

🗺️ Roadmap

Our journey to a fully featured lore translator:

    Robust & Automated CLI MVP: Finalize the command-line translator with modularity and automated build processes.

    Initial GUI & API Key Storage: Introduce a basic graphical interface and secure API key management.

    GUI-based Prompt Management: Implement the interface for selecting, editing, and creating prompts.

    Local Glossary System (SQLite): Develop the local database for managing lore terms and jargon.

    Basic Project Management (Text): Enable loading, segmenting, and managing text-based translations locally.

    OCR Integration: Add functionality for extracting text from images and PDFs.

    Enhanced UX & In-App Browser: Significant improvements to user experience and integrated translation viewing.

    AI Prompt Generation: Allow Gemini itself to assist in creating and refining translation prompts.

    Level 1 Collaboration (Import/Export): Enable manual sharing of project data for basic collaboration.

    Full Collaborative Platform (Backend): Implement a dedicated server for real-time, seamless collaborative translation efforts.

🚧 Key Challenges & Considerations

Developing a cross-platform desktop application with a dual-language stack involves unique complexities:

    Dual Language Development: Managing development across Dart (Flutter) and Python (Backend).

    Inter-Process Communication: Reliably starting and managing the Python service from the Flutter app and facilitating communication via a local REST API.

    Complex Packaging: Creating unified installers for each OS that bundle both the Flutter application and the Python service seamlessly.

    API Key Security: Implementing secure storage for the Gemini API key (e.g., using keyring or encryption).

    OCR Dependencies: Managing and packaging external OCR dependencies (like Tesseract and its language data).

    Threading & Asynchronicity: Ensuring the UI remains responsive during long-running operations (API calls, OCR processing).

    Robust Error Handling: Providing user-friendly error messages for the non-technical target audience.

    Real-time Collaboration: The most complex feature, likely requiring a dedicated remote backend infrastructure.

🙏 Contributing

We welcome contributions of all kinds! Whether it's code, documentation, UI/UX design, or translations for new languages, your help is invaluable.

Please refer to our CONTRIBUTING.md (coming soon!) for detailed guidelines on how to get involved.
📜 License

This project is open-source and distributed under the MIT License. See the LICENSE file for more details.
✉️ Contact

For questions, feedback, or collaborations, please open an issue on our GitHub Issues page or reach out to the project maintainers.