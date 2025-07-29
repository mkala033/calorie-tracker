Daily Calorie & Protein Tracker
A clean, modern, and responsive web application to track your daily food intake. This app helps you monitor your calories and protein consumption with real-time data synchronization, powered by Google Firebase.



➡️ Live Demo: You can link to your GitHub Pages site here!

(Note: Please replace the image link above with a screenshot of your actual application!)

✨ Features
Secure User Authentication: Sign up, log in, and sign out securely using Firebase Authentication (Email/Password).

Full CRUD Functionality: Create, Read, Update, and Delete your daily food entries.

Real-time Data Sync: Your data is saved instantly to Firestore and available across all your devices.

Automatic Daily Summaries: The dashboard automatically calculates and displays the total calories and protein for the selected day.

Smart Food Suggestions: An intuitive autocomplete feature suggests common food items as you type, speeding up data entry.

Responsive Design: The interface, built with Tailwind CSS, is fully responsive and works seamlessly on desktop, tablets, and mobile devices.

Interactive UI:

Dynamic forms for both adding and editing entries.

A scrollable log table to view all entries for a given day.

User-friendly notifications for successful actions or errors.

Date Picker: Easily navigate between different days to view or add logs.

🛠️ Tech Stack
This project is built with modern, lightweight technologies:

Frontend: HTML5, CSS3, JavaScript (ES Modules)

Styling: Tailwind CSS

Backend & Database: Google Firebase

Firestore: For real-time NoSQL database storage.

Firebase Authentication: For managing user accounts.

🚀 Getting Started
To get a local copy up and running, follow these simple steps.

Prerequisites
You need a Google account to create a Firebase project.

Installation
Clone the repository

Bash

git clone https://github.com/your-username/your-repository-name.git
Set up Firebase

Go to the Firebase Console.

Click "Add project" and give it a name (e.g., "CalorieTracker").

Once the project is created, click the web icon </> to add a web app.

Register the app and Firebase will provide you with a firebaseConfig object. Copy this object.

In your new project's dashboard, go to the Build section in the left sidebar.

Click on Firestore Database -> Create database. Start in test mode for easy setup.

Click on Authentication -> Get started. Select Email/Password as a sign-in method and enable it.

Add your Firebase Configuration

Open the index.html file (or whatever you have named it).

Find the <script type="module"> tag at the bottom.

Locate the firebaseConfig object and replace the placeholder values with the keys you copied from your Firebase project.

JavaScript

// --- Initialization ---
document.addEventListener('DOMContentLoaded', async () => {
    const firebaseConfig = {
        apiKey: "YOUR_API_KEY",
        authDomain: "YOUR_PROJECT_ID.firebaseapp.com",
        projectId: "YOUR_PROJECT_ID",
        storageBucket: "YOUR_PROJECT_ID.appspot.com",
        messagingSenderId: "YOUR_SENDER_ID",
        appId: "YOUR_APP_ID",
        measurementId: "YOUR_MEASUREMENT_ID" // Optional
    };

    const app = initializeApp(firebaseConfig);
    // ... rest of the code
});
Run the Application

Since this is a single HTML file with no build step, you can simply open it in your web browser.

For the best experience (especially with ES Modules), it's recommended to use a local server. If you use Visual Studio Code, you can install the Live Server extension, right-click the index.html file, and select "Open with Live Server".

🔥 Firebase Data Structure
The data for each user is stored in Firestore using the following structure. Each day's log is a separate document, which makes querying efficient.

/artifacts/{appId}/users/{userId}/logs/{YYYY-MM-DD}
artifacts: A top-level collection to organize app data.

users: A sub-collection containing a document for each user, identified by their userId from Firebase Auth.

logs: A sub-collection where each document is named after a date (e.g., 2025-07-29) and contains an array of that day's food entries.

📜 License
This project is licensed under the MIT License. See the LICENSE file for details.
