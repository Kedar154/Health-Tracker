# Main IDeas

APP : 2

WEBSITE : 1

DATABASE : 1

# Tab 1

Whats the Plan BOSS

Great choice 👍  
**Idea \#6 (Rural Health Awareness & Reminder App)** is *perfect* for Simrol — high impact, simple to explain, and very relevant.

Below is a **complete hackathon-ready breakdown** you can directly use.

---

# **🩺 Project Title**

**“SwasthyaSetu – Rural Health Awareness & Reminder Platform”**

*(Swasthya \= Health, Setu \= Bridge)*

---

## **🎯 Problem Statement (Simrol Context)**

In Simrol village and nearby college areas:

* People **miss vaccination dates**  
* Chronic patients forget **regular medicines**  
* Lack of **basic health awareness**  
* Language & literacy barriers  
* No single source for **nearby health services**

This leads to **preventable illnesses** and late medical intervention.

---

## **💡 Solution Overview**

**SwasthyaSetu** is a **local-language mobile app \+ SMS system** that:

* Sends **health reminders**  
* Provides **simple health education**  
* Shares **nearby clinic & hospital info**  
* Works even for people with **low literacy & poor internet**

---

## **👥 Target Users**

* Villagers of **Simrol**  
* Elderly people  
* Pregnant women  
* Parents of young children  
* College students staying nearby

---

## **✨ Key Features**

### **1️⃣ Health Reminders ⏰**

* Vaccination reminders (child & adult)  
* Medicine reminders  
* Monthly health check alerts

👉 Notifications \+ optional SMS

---

### **2️⃣ Local Language Health Tips 🗣️**

* Short daily health tips  
* Audio support for non-readers  
* Topics:  
  * Hygiene  
  * Nutrition  
  * Seasonal diseases  
  * Mental health

---

### **3️⃣ Nearby Healthcare Finder 🏥**

* Shows:  
  * PHC (Primary Health Centre)  
  * Clinics  
  * Pharmacies  
* Directions using maps

---

### **4️⃣ Symptom Awareness (Not Diagnosis) ⚠️**

* User selects symptoms  
* App gives **basic advice**  
* Suggests **when to visit a doctor**

⚠️ *No medical diagnosis – awareness only*

---

### **5️⃣ Emergency Health Contacts 🚑**

* One-tap call to:  
  * Ambulance  
  * Local health worker (ASHA)  
  * Nearby hospital

---

## **🧱 System Architecture (Simple & Clear)**

User (Flutter App)  
        |  
        v  
Firebase Authentication  
        |  
Firebase Realtime Database  
        |  
Cloud Functions  
        |  
Notifications / SMS  
        |  
Google Maps API (Nearby Hospitals)

---

## **🧰 Google Technologies Used**

| Purpose | Technology |
| ----- | ----- |
| App Development | **Flutter** |
| Authentication | **Firebase Auth** |
| Data Storage | **Firebase Realtime DB** |
| Notifications | **Firebase Cloud Messaging** |
| Maps & Location | **Google Maps API** |
| Voice Support | **Google Text-to-Speech** |
| Hosting (optional) | **Firebase Hosting** |

---

## **🌍 Social Impact**

* Reduces missed vaccinations  
* Improves health awareness  
* Helps elderly & low-literacy users  
* Prevents minor issues from becoming serious  
* Scalable to **any rural village**

---

## **🚀 Hackathon Demo Plan (Very Important)**

### **Live Demo Flow:**

1. User logs in  
2. Selects:  
   * Age  
   * Language  
   * Health category  
3. Sets a medicine reminder  
4. Receives notification  
5. Shows nearby PHC on map  
6. Plays an audio health tip

⏱️ Perfect **3–4 minute demo**

---

## **🗣️ Pitch Script (Judges Love This)**

“In villages like Simrol, people don’t fall sick because hospitals are far —  
they fall sick because **information is far**.  
SwasthyaSetu brings healthcare awareness directly to their phones, in their language, at the right time.”

---

## **👨‍👩‍👦 Team Role Distribution**

(4-member team example)

* **Member 1:** Flutter UI  
* **Member 2:** Firebase backend  
* **Member 3:** Google Maps \+ Notifications  
* **Member 4:** Pitch \+ Research \+ UX

---

## **🔮 Future Scope (Extra Points)**

* Integration with ASHA workers  
* Offline health tips  
* AI-based risk prediction  
* Wearable data integration

---

## **🏆 Why This Can Win**

✅ Local problem  
✅ Clear Google tech usage  
✅ Social impact  
✅ Easy demo  
✅ Scalable

---

Next, I can:

* Design **UI wireframes**  
* Create **database schema**  
* Write **Firebase rules**  
* Prepare **PPT slides**  
* Even help with **app name/logo**

What do you want next? 😄

Login

Medicine info

## 

## 

## **Patient App (Android – minimal, offline-first)**

* One-time pairing with patient profile (code / QR) // login ID and Password  
* Store medicine schedule **locally**  
* Trigger reminders at scheduled times  
* Play **voice reminder (TTS)** in local language  
* Show popup with:  
  * **Green: Taken**  
  * **Red: Not taken**  
* If no “Taken” → remind again after 30 minutes  
* Decide **Taken vs Missed locally**  
* Store each response in **local queue**  
* Sync queued data to server when internet is available

**Does NOT do:**

* No login/password  
* No editing schedules  
* No history view  
* No dashboards  
* No family alerts

---

## **Website \+ Backend (caregiver / monitoring side)**

* Create patient profiles  
* Enter medicine schedules  
* Pair patient app with profile  
* Store patient & schedule data  
* Receive adherence logs from app  
* Show **weekly medication history**  
* Detect repeated missed doses  
* Notify family member (SMS / call / demo alert)  
* Provide simple dashboard for nurse / ASHA

**Does NOT do:**

* No reminder timing  
* No voice playback  
* No patient interaction  
* No real-time monitoring

# Tab 2

Perfect question — this is exactly what judges and real users care about.  
Below is the **exact, step-by-step, implementation-level workflow** for a **Medicine Reminder System**, written so you can **directly build it** using **Flutter \+ Firebase \+ Google services**.

I’ll cover:

1. User flow (what the user does)  
2. System flow (what happens in the backend)  
3. Data model (exact fields)  
4. Notification logic (how reminders actually fire)  
5. Edge cases (missed doses, phone off, etc.)

---

# **🩺 Medicine Reminder System – Exact Workflow**

## **🔁 1\. USER WORKFLOW (FRONTEND – Flutter)**

### **Step 1: User Login / Registration**

* User opens app  
* Logs in using:  
  * Phone number (OTP) **(best for Simrol)**  
* Language selection (Hindi / Marathi / English)

---

### **Step 2: Add Medicine**

User taps **“Add Medicine”**

User inputs:

* Medicine Name (Text / Voice input)  
* Medicine Type (Tablet / Syrup / Injection)  
* Dosage (e.g., 1 tablet)  
* Frequency:  
  * Once a day  
  * Twice a day  
  * Thrice a day  
  * Custom  
* Start Date  
* End Date  
* Time(s) of day (e.g., 8:00 AM, 2:00 PM)  
* Reminder type:  
  * Notification  
  * Notification \+ SMS  
* Audio reminder: ON/OFF

👉 On submit → Data sent to Firebase

---

## **🔁 2\. BACKEND WORKFLOW (Firebase)**

### **Step 3: Store Medicine Data**

Data stored in **Firebase Realtime DB / Firestore**

users/  
  userId/  
    medicines/  
      medicineId/  
        name: "Paracetamol"  
        dosage: "1 tablet"  
        frequency: "2"  
        times: \["08:00", "20:00"\]  
        startDate: "2025-01-10"  
        endDate: "2025-01-15"  
        reminderType: "notification"  
        audio: true  
        active: true

---

### **Step 4: Schedule Reminders (CRITICAL STEP)**

Since Firebase **cannot trigger notifications by itself**, we use:

### **✅ Option A (Best for Hackathon):**

**Local Notifications \+ Firebase backup**

#### **Workflow:**

* Flutter schedules **local notifications** using `flutter_local_notifications`  
* Notification times calculated from:  
  * Start Date  
  * End Date  
  * Selected Times

Example:

Jan 10 → 8:00 AM, 8:00 PM  
Jan 11 → 8:00 AM, 8:00 PM  
...  
Jan 15 → 8:00 PM

👉 These are stored locally on the phone  
👉 Works even without internet

---

### **Step 5: Push Notification Content**

Notification message:

Time to take your medicine 💊  
Paracetamol – 1 tablet

If audio reminder ON:

* Google Text-to-Speech plays:  
  “Paracetamol lene ka samay ho gaya hai”

---

## **🔁 3\. NOTIFICATION EXECUTION FLOW**

### **Step 6: Notification Fires**

At scheduled time:

* Phone shows notification  
* Audio alert plays (if enabled)  
* Vibration (optional)

User options:

* ✅ Taken  
* ⏰ Snooze (10 / 15 / 30 min)  
* ❌ Skip

---

### **Step 7: User Response Handling**

User taps action:

#### **If "Taken":**

* App records:

taken: true  
takenTime: timestamp

#### **If "Snooze":**

* New notification scheduled

#### **If "Skip":**

* Mark skipped  
* Log reason (optional)

---

## **🔁 4\. MISSED DOSE HANDLING (IMPORTANT)**

### **Scenario: User ignores notification**

After X minutes (e.g., 30 min):

* App checks:

if taken \== false

Then:

* Send **missed dose alert**  
* Optional SMS to caregiver

Message:

You missed your medicine dose.  
Please take it if advised by doctor.

---

## **🔁 5\. DAILY HEALTH LOG (FOR FUTURE AI)**

Each dose creates a log:

medicineLogs/  
  userId/  
    logId/  
      medicineName: "Paracetamol"  
      scheduledTime: "08:00"  
      status: "taken" / "missed"  
      timestamp: ...

This helps:

* Show adherence percentage  
* Predict missed doses  
* Future ML integration

---

## **🧠 6\. BACKGROUND TASKS (OPTIONAL BUT IMPRESSIVE)**

### **Daily Summary Notification**

At night:

Today’s Summary:  
✔ Medicines taken: 3  
❌ Missed: 1

---

## **📊 7\. UI SCREENS REQUIRED**

1. Login Screen  
2. Add Medicine Screen  
3. Medicine List Screen  
4. Reminder Notification UI  
5. Daily History Screen

---

## **🧪 8\. EDGE CASES HANDLED**

| Case | Solution |
| ----- | ----- |
| Phone off | Local notifications resume |
| No internet | Works offline |
| App killed | Notifications still fire |
| Elderly user | Audio \+ big buttons |
| Language issue | Local language support |

---

## **🏆 HOW TO EXPLAIN THIS TO JUDGES**

Say this line 👇

“Our medicine reminder system works even without internet using local scheduling, while securely syncing data to Firebase for long-term tracking and health analytics.”

---

## **🚀 NEXT STEPS (I CAN HELP WITH)**

* Flutter notification code  
* Firebase schema design  
* UI wireframes  
* Demo script  
* PPT slide content

Just tell me what you want next 👍

# Tab 4

## **🧩 How the making of this project is split**

### **📱 Patient App (Android – reminder side)**

**Who works on this:** 1 person (or 2 max)

**Responsibilities:**

* One-time pairing with patient profile  
* Store medicine schedule locally  
* Trigger reminders at correct time  
* Play voice reminder (TTS)  
* Show **Taken / Not Taken** buttons  
* Handle second reminder after 30 min  
* Store results locally (offline)  
* Sync results when internet is available

**Key point:**  
App handles **time \+ voice \+ offline**  
Nothing else.

---

### **🌐 Website (Caregiver side)**

**Who works on this:** 1 person

**Responsibilities:**

* Patient creation form  
* Medicine schedule input  
* Pairing code / QR generation  
* Weekly adherence view (green/red)  
* Simple dashboard for nurse / ASHA

**Key point:**  
Website is **configuration \+ monitoring**, not reminders.

---

### **🧠 Backend (Glue layer)**

**Who works on this:** 1 person (can overlap with website)

**Responsibilities:**

* Store patient profiles  
* Store schedules  
* Receive adherence logs from app  
* Aggregate weekly data  
* Trigger family alerts on repeated misses

**Key point:**  
Backend is **data \+ logic**, not timing.

---

## **🔧 Google technologies used (clear and defensible)**

This is important — say these **explicitly**.

---

### **☁️ Firebase**

Used for:

* Patient data storage  
* Medicine schedules  
* Adherence logs  
* Easy backend without server setup

Why judges like it:

* Fast to build  
* Scales well  
* Very hackathon-friendly

---

### **🔐 Firebase Authentication**

Used for:

* Caregiver / admin login on website  
* Securing patient data

(⚠️ Patient app does **not** use full auth — only pairing)

---

### **🔊 Google Text-to-Speech**

Used for:

* Voice reminders in local language  
* Clear spoken instructions for patients

Why this matters:

* Voice-first design  
* Inclusive for elderly & low-literacy users

---

### **🌐 Google Cloud *(implicit via Firebase)***

Used for:

* Reliable backend infrastructure  
* Secure data storage  
* Automatic scaling

You don’t need to manage servers at all.

---

### **🗺️ *(Optional / Future scope)* Google Maps Platform**

* Clinic location reminders  
* Appointment navigation

Say this as **future work**, not MVP.

---

## **🏗️ Technology stack summary (one slide worth)**

### **Patient App**

* Android  
* Kotlin  
* Google Text-to-Speech  
* Local storage (offline queue)

### **Website**

* HTML  
* CSS  
* JavaScript

### **Backend**

* Firebase Firestore  
* Firebase Auth  
* Firebase Cloud Functions (optional)

---

## **🎯 How to say this confidently to judges**

Use this exact phrasing:

“We split responsibilities clearly.  
The Android app handles voice reminders and offline adherence.  
The website handles configuration and monitoring.  
We use Firebase and Google Text-to-Speech to keep the system scalable, low-cost, and reliable for rural settings.”

This checks **all hackathon boxes**:

* Local problem ✅  
* Google tech ✅  
* Realistic build ✅  
* Clear division of work ✅

---

# WEBSITE

The website is **not for patients**, but for **caregivers (nurses, ASHA workers, or family members)**.

**Core purpose:**  
Configure patient medication schedules and monitor whether medicines are taken properly.

**Key features to include:**

* Caregiver login (simple authentication)  
* Create and manage patient profiles (name, age, phone number, family contact)  
* Add medication schedules for each patient (medicine name, times per day, duration)  
* Generate a one-time pairing code / QR code to connect a patient’s mobile app  
* Receive medication adherence logs from the patient app  
* Display a **weekly medication history** using a simple color system:  
  * Green \= taken  
  * Red \= missed  
* Highlight patients with repeated missed doses  
* Show a basic dashboard listing all patients and their adherence status  
* Trigger a notification/alert to a family contact if multiple doses are missed

**Design requirements:**

* Very simple UI  
* Large text and clear buttons  
* Easy to use on low-end devices  
* No complex charts, no real-time tracking

**What the website does NOT do:**

* Does not send reminders  
* Does not play voice  
* Does not interact directly with patients  
* Does not handle timing or alarms

**Role separation:**

* The **patient mobile app** handles reminders, voice alerts, and offline usage  
* The **website** only configures schedules and monitors adherence

The website should feel reliable, minimal, and suitable for rural healthcare workers.

# APP

**Target user:**  
Elderly or rural patients with low literacy.

**Core purpose:**  
Play voice reminders for medicines at the correct time and record whether the medicine was taken.

---

**App scope (VERY IMPORTANT):**  
This app is **not a full healthcare app**.  
It has **no dashboards, no editing, no history view, and no settings**.

---

**Required features:**

* One-time pairing screen using a pairing code or QR code  
  * This links the app to an existing patient profile created on a website  
  * No usernames or passwords  
* Store medicine schedules **locally on the device**  
* Trigger reminders **offline** at scheduled times  
* Play a **voice reminder using Text-to-Speech** in a local language  
  Example:  
  “It is time to take your blood pressure medicine.”  
* When a reminder triggers, show a **full-screen popup** with:  
  * A large **green “Taken” button**  
  * A large **red “Not taken” button**  
* If “Taken” is pressed → mark the dose as taken  
* If “Not taken” or no response → trigger a second reminder after 30 minutes  
* If the user presses “Taken” in either reminder → dose is marked as taken  
* If the user presses “Not taken” both times or gives no response → dose is marked as missed  
* Store each dose result **locally in an offline queue**  
* When internet becomes available:  
  * Sync all queued dose records to the backend server  
  * Remove records from local storage only after successful upload

---

**What the app must NOT include:**

* No login system  
* No patient data editing  
* No medication list browsing  
* No charts or history  
* No notifications to family  
* No real-time internet dependency

---

**Technical expectations:**

* Android app  
* Kotlin preferred  
* Use Android’s built-in Text-to-Speech  
* Use local storage for offline queue  
* Simple, reliable background scheduling

---

**Design requirements:**

* Extremely simple UI  
* Large buttons  
* High contrast  
* Minimal text

---

**Role separation clarity:**

* This app only handles reminders and user confirmation  
* All configuration, monitoring, and dashboards are handled by a separate website

The final app should feel like a **talking medicine reminder with one confirmation button**, nothing more.

# DATABASE

**Purpose of backend:**  
The backend acts as a **central data store and monitoring layer**, not a reminder engine.

---

### **Core responsibilities**

* Store patient profiles created from a website  
* Store medicine schedules for each patient  
* Link a patient profile to a mobile app using a **one-time pairing code**  
* Receive medication adherence logs from the patient app  
* Aggregate adherence data into a **weekly view**  
* Detect repeated missed doses  
* Trigger a family alert (can be logged or simulated)

---

### **Important design constraint**

* The backend **does NOT handle reminder timing**  
* The backend **does NOT trigger voice or alarms**  
* All reminder timing and offline handling is done by the patient app

---

### **Required data models**

**Patient**

* patient\_id  
* name  
* age  
* phone\_number  
* family\_contact\_number  
* pairing\_code

**MedicineSchedule**

* schedule\_id  
* patient\_id  
* medicine\_name  
* times\_per\_day  
* start\_date  
* end\_date

**DoseLog**

* log\_id  
* patient\_id  
* schedule\_id  
* scheduled\_time  
* actual\_response\_time  
* status (TAKEN / MISSED)

---

### **API endpoints to implement**

* Create patient profile  
* Create / update medicine schedule  
* Generate pairing code  
* Pair patient app using pairing code  
* Receive batch dose logs from patient app (offline sync)  
* Fetch weekly adherence data for a patient  
* Fetch dashboard summary for caregivers

---

### **Offline sync behavior**

* The backend must accept **multiple dose logs in a single request**  
* Logs may arrive late  
* Backend should treat each log as an independent event  
* No real-time guarantees required

---

### **Alert logic**

* If multiple consecutive doses are marked as MISSED:  
  * Trigger a family alert (can be a console log, email, or simulated SMS)

---

### **Technical expectations**

* Simple REST API  
* Beginner-friendly architecture  
* Clear separation between data storage and logic  
* No real-time features  
* No AI or ML

---

### **Recommended stack (but flexible)**

* Node.js with Express **OR** Python with FastAPI  
* Firebase Firestore **OR** SQL database  
* Clean, readable structure suitable for a hackathon MVP

---

The backend should be **minimal, reliable, and easy to reason about**, designed to support a low-connectivity rural healthcare environment.

