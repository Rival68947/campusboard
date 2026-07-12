# CampusBoard

A React + Vite + Supabase based Campus Notice Board application.

This project demonstrates:

- User Authentication
- Profile Management
- Notice Board CRUD
- Realtime Updates
- Notifications
- Supabase Database Integration
- Supabase Storage

---

# Prerequisites

Before running this project, make sure you have:

- Node.js (v18 or later recommended)
- npm
- Git
- A Supabase account

---

# Installation

## Clone the repository

```bash
git clone https://github.com/YOUR_GITHUB_USERNAME/YOUR_REPOSITORY.git
cd CampusBoard
```

## Install dependencies

```bash
npm install
```

---

# Supabase Setup

## Step 1 - Create a Supabase Project

Go to:

https://supabase.com

Create a new project.

Wait until the database finishes provisioning.

---

## Step 2 - Get API Credentials

Copy:

- Project URL
- Publishable Key

(In older Supabase tutorials this may be called the Anon Key.)

---

## Step 3 - Create a .env File

Create a file named

```
.env
```

in the project root.

Add:

```env
VITE_SUPABASE_URL=YOUR_PROJECT_URL
VITE_SUPABASE_ANON_KEY=YOUR_PUBLISHABLE_KEY
```

Example:

```env
VITE_SUPABASE_URL=https://your-project.supabase.co
VITE_SUPABASE_ANON_KEY=sb_publishable_xxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

Restart the development server after creating the `.env` file.

---

# Database Setup

Open:

Supabase Dashboard

→ SQL Editor

→ New Query

Copy the SQL provided below (or in this README if included).

Run the complete SQL script.

After running successfully, the following tables should exist:

- profiles
- notices
- notifications

---

# Storage Setup (Optional)

If avatar uploads are required:

Go to:

Storage

Create a bucket named:

```
avatars
```

Make it Public.

Run the Storage Policies provided below.

---

# Start the Project

```bash
npm run dev
```

Open

```
http://localhost:5173
```

---

# Features

- User Signup/Login
- Secure Authentication
- Create Notices
- Delete Own Notices
- Profile Page
- Avatar Upload
- Realtime Notice Updates
- Notification System

---

# Project Structure

```
src
│
├── components
│   ├── AvatarUpload.jsx
│   ├── Navbar.jsx
│   ├── NoticeCard.jsx
│   ├── NoticeForm.jsx
│   └── NotificationBell.jsx
│
├── context
│   └── AuthContext.jsx
│
├── hooks
│   ├── useNotices.js
│   ├── useNotifications.js
│   └── useRealtimeNotices.js
│
├── pages
│   ├── Dashboard.jsx
│   ├── Login.jsx
│   ├── Profile.jsx
│   └── Signup.jsx
│
├── utils
│
├── supabaseClient.js
│
└── App.jsx
```

---

# Troubleshooting

## White Screen

Open Developer Tools

```
F12
```

Go to:

```
Console
```

If you see

```
supabaseUrl is required
```

then your `.env` file is missing or incorrectly configured.

Make sure it contains:

```env
VITE_SUPABASE_URL=...
VITE_SUPABASE_ANON_KEY=...
```

Restart the development server afterwards.

---

## npm ERR! Could not read package.json

You are not inside the project folder.

Run:

```bash
cd CampusBoard
```

Then:

```bash
npm install
```

---

## 404 when Posting Notices

This usually means the SQL schema has not been executed.

Run the SQL script in the Supabase SQL Editor.

Verify that the following tables exist:

- profiles
- notices
- notifications

---

## Notices are Saved but Not Visible

Check:

- SQL script executed successfully
- notices table exists
- Realtime is configured (if using realtime)
- Browser Console for errors
- Browser Network tab

If the POST request returns

```
201 Created
```

then the notice has been inserted successfully.

---

# Important

This repository does **NOT** include the `.env` file.

Each user must create their own Supabase project and configure their own:

- Project URL
- Publishable Key

Do not commit your `.env` file to GitHub.

---

# Technologies Used

- React
- Vite
- Supabase
- JavaScript
- CSS

---

# License

This project is intended for educational purposes.
