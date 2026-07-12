# CampusBoard

A React + Vite + Supabase based Campus Notice Board application.

This project demonstrates:

- User Authentication
- Profile Management
- Notice Board CRUD Operations
- Realtime Notice Updates
- Notifications
- Supabase Database Integration
- Supabase Storage

---

# Prerequisites

Before running this project, make sure you have:

- Node.js (v18 or later recommended)
- npm
- Git
- A Supabase Account

---

# Installation

## Clone the Repository

```bash
git clone https://github.com/Rival68947/campusboard.git
cd CampusBoard
```

## Install Dependencies

```bash
npm install
```

---

# Supabase Setup

## Step 1 - Create a Supabase Project

1. Go to https://supabase.com
2. Sign in.
3. Click **New Project**.
4. Choose your organization.
5. Enter a project name.
6. Set a database password.
7. Choose a region.
8. Wait for the project to finish provisioning.

---

## Step 2 - Get API Credentials

Open your Supabase project.

Copy:

- Project URL
- Publishable Key

> **Note:** Older tutorials may call this the **Anon Key**. In the current Supabase UI, use the **Publishable Key**.

---

## Step 3 - Create the Environment File

Create a file named:

```
.env
```

inside the project root (same folder as `package.json`).

Add:

```env
VITE_SUPABASE_URL=https://your-project.supabase.co
VITE_SUPABASE_ANON_KEY=your_publishable_key
```

Example:

```env
VITE_SUPABASE_URL=https://xxxxxxxxxxxxxxxx.supabase.co
VITE_SUPABASE_ANON_KEY=sb_publishable_xxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

After creating the `.env` file, restart the development server.

---

# Database Setup

1. Open Supabase.
2. Go to **SQL Editor**.
3. Click **New Query**.
4. Copy the SQL provided below (or included later in this README).
5. Paste it into the editor.
6. Click **Run**.

After running successfully, you should see the following tables:

- profiles
- notices
- notifications

---

# Storage Setup (Optional)

If avatar uploads are required:

1. Open **Storage**.
2. Create a bucket named:

```
avatars
```

3. Make it **Public**.
4. Apply the Storage Policies from the SQL/README if provided.

---

# Run the Project

```bash
npm run dev
```

Open:

```
http://localhost:5173
```

---

# Features

- User Signup
- User Login
- Secure Authentication
- Create Notices
- Delete Own Notices
- Profile Management
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

## 1. White Screen

Press:

```
F12
```

Open the **Console**.

If you see:

```
supabaseUrl is required
```

Make sure:

- `.env` exists.
- `.env` is in the project root.
- `VITE_SUPABASE_URL` is correct.
- `VITE_SUPABASE_ANON_KEY` contains your Publishable Key.

Restart the dev server afterwards.

---

## 2. npm ERR! Could not read package.json

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

## 3. 404 Error When Posting Notices

This usually means the database tables were not created.

Run the SQL script in Supabase SQL Editor.

Verify that these tables exist:

- profiles
- notices
- notifications

---

## 4. Notices Not Appearing

Open:

```
F12
→ Network
```

Check the request to:

```
/rest/v1/notices
```

If the response is:

```
201 Created
```

the notice was inserted successfully.

Then verify:

- SQL script executed successfully.
- `notices` table exists.
- Realtime is configured (if required).
- Browser Console has no errors.

---

## 5. Authentication Doesn't Work

Verify that:

- `.env` contains the correct Project URL.
- `.env` contains the correct Publishable Key.
- Supabase Authentication is enabled.
- The project was restarted after editing `.env`.

---

# Technologies Used

- React
- Vite
- Supabase
- JavaScript
- CSS

---

# Important

This repository **does not include** the `.env` file.

Every user should:

- Create their own Supabase project.
- Use their own Project URL.
- Use their own Publishable Key.

Do **not** upload your `.env` file to GitHub.

---
Deployment link-https://campusboard-ftznqe9gy-rival68947.vercel.app/login

# License

This project is intended for educational purposes.

