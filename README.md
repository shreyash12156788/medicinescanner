# 🩺 MediScan AI

### AI-Powered Healthcare Assistant for Android

MediScan AI is an AI-powered Android healthcare assistant designed to help users understand medicine labels, prescriptions, and medical laboratory reports.

The application combines **Google ML Kit OCR, Gemini AI, Firebase, and Android technologies** to scan medical documents, extract text, analyze medical information, track health history, and provide easy-to-understand explanations.

> ⚠️ **Medical Disclaimer:** MediScan AI is intended for informational and educational purposes only. It does not replace professional medical advice, diagnosis, or treatment from a qualified healthcare professional.

---

## ✨ Features

### 📄 1. Document & Prescription Scanner

- Scan prescriptions, medicine labels, and medical reports.
- Uses Google ML Kit Document Scanner.
- Import documents from the device gallery.
- Supports image-based documents.
- Automatic document cropping and enhancement.
- High-quality document capture.

---

### 🔍 2. OCR Text Extraction

Extract text from:

- Medicine boxes
- Medicine strips/blister packs
- Prescriptions
- Medical laboratory reports
- Other medical documents

Powered by:

**Google ML Kit Text Recognition**

---

### 🤖 3. AI Medical Report Analysis

MediScan AI uses **Google Gemini AI** to analyze extracted medical text.

The AI can:

- Explain complex medical terminology.
- Summarize medical reports.
- Explain laboratory test parameters.
- Identify values outside the provided reference range.
- Explain possible significance of abnormal values.
- Convert technical medical information into simpler language.
- Provide general informational guidance.

---

### 💊 4. Medicine Information

Users can search or scan medicines to view information such as:

- Medicine name
- Active ingredients
- Uses
- Dosage information
- Warnings
- Safety information
- General medicine details

Medicine information can be retrieved from local asset data such as:

```text
medicines.json

and can also be integrated with remote data sources.

🔄 5. Alternative Medicine Lookup

The application supports medicine alternative discovery.

Users can explore:

Generic alternatives
Brand alternatives
Same-composition medicines
Alternative medicine details

Main components include:

AlternativeMedicineDetailActivity
SameMedicineListActivity

Medicine substitutions should always be confirmed with a qualified doctor or pharmacist.

🔐 6. Authentication & User Profile

Secure user authentication powered by Firebase Authentication.

Includes:

User Registration
Login
Forgot Password
User Profile
Edit Profile
Secure authentication flow

Main activities:

LoginActivity
RegisterActivity
ForgotPasswordActivity
ProfileActivity
EditProfileActivity
☁️ 7. Health History & Cloud Sync

Users can store their health-related scan history using Cloud Firestore.

Stored information can include:

Scanned reports
OCR results
AI explanations
Report history

Users can access their stored history across supported devices.

📊 8. Report Comparison & Health Tracking

MediScan AI allows users to compare previous and current laboratory reports.

Users can:

Compare historical reports.
Track changes in health metrics.
View previous test results.
Identify changes between reports.

Main activity:

ReportComparisonActivity
⏰ 9. Medicine Reminders

Users can schedule medication reminders.

The application uses:

AndroidX WorkManager

for background reminder processing.

Features include:

Medicine reminder scheduling
Background reminder execution
System notifications
Medication schedule management

Main worker:

MedicineReminderWorker
🏗️ Application Architecture

The application follows a modular Android architecture with dedicated activities and components for scanning, OCR, AI analysis, medicine information, authentication, health history, and reminders.

Core Flow
┌──────────────────────┐
│    User / Dashboard  │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│   Document Scanner   │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│    ML Kit OCR        │
│  Text Recognition    │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│     Gemini AI        │
│ Medical Analysis     │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│ Explanation / Report │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│    Firestore         │
│   Health History     │
└──────────────────────┘
📱 Main Activities
Activity	Purpose
DashboardActivity	Main application dashboard
ScannerActivity	Document scanning and capture
OCRResultActivity	Display and edit extracted OCR text
AIExplanationActivity	Gemini AI medical analysis
MedicineActivity	Medicine search and listing
MedicineDetailActivity	Medicine information
AlternativeMedicineDetailActivity	Alternative medicine information
SameMedicineListActivity	Same-composition medicine list
HealthHistoryActivity	Previous scans and reports
ReportComparisonActivity	Compare historical reports
LoginActivity	User login
RegisterActivity	User registration
ForgotPasswordActivity	Password recovery
ProfileActivity	User profile
EditProfileActivity	Edit profile information
🛠️ Technology Stack
Android Development
Java
XML
Android Studio
Material Design Components
ConstraintLayout
RecyclerView
CardView
ViewBinding
🤖 Machine Learning & OCR
Google ML Kit Text Recognition
Google ML Kit Document Scanner
GmsDocumentScanner
🧠 Generative AI
Google Gemini API
Retrofit 2
Gson
☁️ Firebase
Firebase Authentication
Cloud Firestore
Firebase Analytics
⚙️ Background Processing
AndroidX WorkManager
Android Notifications
📦 Important Dependencies
// Firebase
implementation 'com.google.firebase:firebase-auth'
implementation 'com.google.firebase:firebase-firestore'
implementation 'com.google.firebase:firebase-analytics'

// ML Kit OCR
implementation 'com.google.mlkit:text-recognition'

// Android UI
implementation 'com.google.android.material:material'
implementation 'androidx.constraintlayout:constraintlayout'
implementation 'androidx.recyclerview:recyclerview'

// Networking
implementation 'com.squareup.retrofit2:retrofit'
implementation 'com.squareup.retrofit2:converter-gson'

// Background Processing
implementation 'androidx.work:work-runtime'

Dependency versions may vary depending on the project configuration.

🔐 Security Considerations

The application handles potentially sensitive health-related information.

Recommended security practices include:

Never hardcode API keys in the source code.
Use secure Firebase Security Rules.
Validate Firestore access permissions.
Avoid storing unnecessary medical information.
Protect sensitive user data.
Use HTTPS for network communication.
Keep API credentials outside the public repository.
🚀 Getting Started
1. Clone the Repository
git clone https://github.com/YOUR_USERNAME/mediscan-ai.git
2. Open in Android Studio

Open the cloned project using Android Studio.

3. Configure Firebase

Create a Firebase project and configure:

Firebase Authentication
Cloud Firestore
Firebase Analytics

Add your:

google-services.json

to the appropriate Android app directory.

4. Configure Gemini API

Create/configure your Gemini API access and connect it through the application's networking layer.

Do not commit API keys to GitHub.

5. Build & Run

Sync Gradle and run the application on:

Android Emulator
Physical Android Device
📂 High-Level Project Structure
MediScanAI/
│
├── app/
│   └── src/
│       └── main/
│           ├── java/
│           │   └── .../
│           │
│           ├── res/
│           │   ├── layout/
│           │   ├── drawable/
│           │   ├── mipmap/
│           │   └── values/
│           │
│           └── AndroidManifest.xml
│
├── assets/
│   └── medicines.json
│
├── build.gradle
├── settings.gradle
└── README.md
🔄 Application Workflow
Medicine Scanning
Scan Medicine
      ↓
Document/Image Processing
      ↓
ML Kit OCR
      ↓
Extract Medicine Name
      ↓
Medicine Database
      ↓
Medicine Details
Medical Report Analysis
Scan Report
     ↓
Document Scanner
     ↓
ML Kit OCR
     ↓
Extract Text
     ↓
Gemini AI
     ↓
Medical Explanation
     ↓
Save to Health History
🎯 Project Goals

MediScan AI aims to make medical information easier to understand by combining:

📱 Mobile technology
🤖 Artificial Intelligence
🔍 OCR
☁️ Cloud computing
💊 Medicine information
📊 Health history tracking

The goal is to provide users with a convenient interface for understanding and organizing medical information.

🔮 Future Enhancements

Potential future improvements include:

📈 Advanced health trend visualization
🌐 Multi-language medical explanations
🎙️ Voice-based AI interaction
📄 PDF report generation
🔔 Advanced medication scheduling
🩺 Doctor consultation integration
🔐 Enhanced privacy controls
🧬 Personalized health insights
📊 Advanced laboratory trend analytics
👨‍💻 Developer

Shreyash Chavan

Computer Engineering Background | Android Developer | AI & Cybersecurity Explorer

Interested in:

Android Development
Artificial Intelligence
Cybersecurity
Cloud Security
AI-powered Applications
⭐ Support

If you find MediScan AI useful, consider giving the repository a ⭐ on GitHub.

⚠️ Disclaimer

MediScan AI provides informational assistance only.

It should not be used to:

Diagnose medical conditions
Replace a doctor
Change prescribed medication
Determine medication dosage independently
Make emergency medical decisions

Always consult a qualified healthcare professional for medical diagnosis, treatment, and medication decisions.
