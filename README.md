
CareBridge1 - AI-Powered Telemedicine Platform

Welcome to CareBridge1, a prototype web application for a modern telemedicine service. This platform connects patients with doctors and interns, using AI to assist with preliminary symptom analysis and streamlining the review process.

Author

Devesh Reddy Pusalapati

Features

Multi-Role Authentication: Separate login and registration flows for Patients, Doctors, and Interns.

AI Symptom Checker: Patients can submit their symptoms via:

Text description

Image uploads

Speech-to-Text (using the Web Speech API)

Professional Review Queue: All patient submissions (including chat inquiries) are sent to a central queue where Doctors and Interns can review the AI's preliminary analysis, add their own notes, and send feedback to the patient.

Doctor-Patient Appointment System: Patients can browse a list of public-facing doctors and request appointments. Doctors can then approve or decline these requests from their dashboard.

Patient Medical Records: Patients have a dedicated page to view their entire submission history, including the AI analysis and the doctor's official response.

Conversational Chatbot: A floating chatbot answers common questions ("About Us", "Why Us", "How to Use") and allows logged-in patients to submit a custom query directly to the professional review queue.

Multilingual Support: The UI supports English (en), Kannada (kn), and Hindi (hi).

Tech Stack

Frontend: HTML, CSS, Vanilla JavaScript

Styling: Tailwind CSS (loaded via CDN)

Backend: Firebase

Authentication: For user sign-in and role management.

Firestore: NoSQL database for storing user profiles, analysis cases, appointments, and notifications.

Storage: For hosting patient-uploaded medical images.

APIs: Web Speech API (for voice-to-text).

Installation & Setup

This project is a single HTML file but requires a Firebase project to function.

1. Firebase Project Setup

Create Project: Go to the Firebase Console and create a new project.

Add Web App: In your project's overview, add a new "Web" app (click the </> icon).

Get Config: Copy the firebaseConfig object. It will look like this:

const firebaseConfig = {
  apiKey: "AIza...",
  authDomain: "your-project-id.firebaseapp.com",
  projectId: "your-project-id",
  storageBucket: "your-project-id.appspot.com",
  messagingSenderId: "...",
  appId: "1:..."
};


Paste Config: Open i1f.html in a text editor. Find the const firebaseConfig = { ... }; (around line 140) and replace the entire object with the one you just copied from your Firebase project.

Enable Auth: In the Firebase Console, go to Authentication -> Sign-in method and enable the Email/Password provider.

Enable Firestore: Go to Firestore Database -> Create database.

Start in Test Mode to get it working quickly.

IMPORTANT (Security): After it's working, go to the Rules tab and paste the contents of the firestore.rules file (provided separately) to secure your app.

Enable Storage: Go to Storage -> Get started and create a default storage bucket.

2. How to Run

You cannot just double-click the i1f.html file. The browser's security rules will block the Web Speech API. You must run it from a local server.

The Easiest Way (using VS Code):

Open the project folder in Visual Studio Code.

Install the "Live Server" extension from the VS Code Marketplace.

Right-click on i1f.html in the file explorer.

Select "Open with Live Server".

Your browser will automatically open with the correct URL (like http://127.0.0.1:5500/i1f.html).

The Python Way (if you have Python):

Open a terminal or command prompt in the folder containing i1f.html.

Run this command (for Python 3):

python -m http.server


Open your browser and manually go to http://localhost:8000/i1f.html.

3. Using the App

Once the app is running, use the Register functionality to create three separate accounts:

One Patient

One Doctor

One Intern

Log in with each account to see the different dashboards and test the complete workflow.