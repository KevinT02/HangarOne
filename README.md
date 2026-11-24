<div align="center">

# ✈️ HangarOne

### The logbook tracker for Canadian AME apprentices

Log your Transport Canada tasks, track your hours, and watch your licence progress grow, all in one clean, mobile-friendly page.

![Made with HTML](https://img.shields.io/badge/made%20with-HTML%20%2B%20JS-1f6feb?style=for-the-badge)
![Firebase](https://img.shields.io/badge/backend-Firebase-0b3a8f?style=for-the-badge)
![No build step](https://img.shields.io/badge/build-none-60a5fa?style=for-the-badge)
![Mobile friendly](https://img.shields.io/badge/mobile-friendly-2f80ff?style=for-the-badge)

[Features](#-features) · [Quick start](#-quick-start) · [How it saves data](#-how-your-data-is-saved) · [Disclaimer](#-disclaimer)

</div>

---

## 📸 Preview

> Add a screenshot of the dashboard here:
> `![HangarOne dashboard](docs/dashboard.png)`

---

## ✨ Features

| | |
|---|---|
| 📋 **Full task list** | Every task from the logbook pages, ATA chapters 05 to 83 plus the "S" licence sections |
| 🗂️ **Organized by category** | General & Servicing, Airframe Systems, Airframe Structures, Rotorcraft, Powerplant & Propeller, and "S" Licence Structures |
| 📊 **Licence dashboard** | Overall percent complete, tasks logged, total experience, specialty hours and civil hours for **M1, M2, E or S** |
| ⏱️ **Smart hours log** | Enter a start and end date and hours are estimated for you, and you can edit them. Capped at **150 h per calendar month**, as Transport Canada counts experience |
| 🎓 **Training credit** | Add your basic training credit in months. Tick "TC-approved basic training completed" and only the Regulations exam stays on your checklist |
| ✅ **Exam checklist** | Track the exams for your rating |
| 🔐 **Username and password** | No email needed. Your logbook is private to your account |
| 💾 **Backups** | Download a copy of your logbook any time and load it again on a new device |
| 📴 **Works offline** | Keep logging with no signal, and it syncs when you're back online |
| 🪶 **Lightweight storage** | Each person's data is one tiny compressed record, so it fits easily in Firebase's free plan |

---

## 🚀 Quick start

You only need a free Firebase account. There's nothing to install or build.

**1. Create a Firebase project**
Go to the [Firebase console](https://console.firebase.google.com) and add a project.

**2. Turn on sign-in**
Build → Authentication → Sign-in method → enable **Email/Password**.

**3. Create the database**
Build → Firestore Database → Create database (Standard edition, production mode).
Open the **Rules** tab, paste the contents of [`firestore.rules`](firestore.rules), and click **Publish**.

**4. Add your config**
Project settings → Your apps → add a **Web app**, then copy its config into the `cfg` object in `index.html`.

**5. Host it**
Upload `index.html` to any static host. For example, with Firebase Hosting:

```bash
npm install -g firebase-tools
firebase login
firebase init hosting
firebase deploy
```

Then add your site's domain under Authentication → Settings → **Authorized domains**.

> 💡 You don't need Cloud Storage. HangarOne uses only Authentication, Firestore and Hosting, which are all on the free Spark plan.

---

## 🔒 How your data is saved

- Usernames are turned into a private fake address (`username@ame-logbook.app`) so no real email is needed.
- Each user has **one Firestore record** that holds their whole logbook as a compact, compressed string.
- Changes save about two seconds after you stop typing, and nothing is written if nothing changed.
- The app reads your data once at sign-in and doesn't listen live, which keeps usage tiny.
- Security rules make sure users can **only read and write their own record**.

> ⚠️ There is no password reset because there's no email. Remember your password, and download a backup from **Save / restore** now and then.

---

## 🗂️ Project structure

```
HangarOne/
├── index.html        # the whole app: page, styles and code
├── firestore.rules   # database security rules
└── README.md
```

---

## 🧰 Built with

- Plain **HTML, CSS and JavaScript**, no framework and no build step
- [Firebase Authentication](https://firebase.google.com/docs/auth) and [Cloud Firestore](https://firebase.google.com/docs/firestore)
- Firebase SDK loaded from Google's CDN

---

## 📌 Disclaimer

HangarOne is a **personal tracking aid**, not an official record, and it is **not affiliated with or endorsed by Transport Canada**. Your signed, employer-verified logbook and Transport Canada's current requirements always take precedence. The requirements shown (experience months, categories, exams) are summarized from Transport Canada's AME licensing pages (CAR 403 / AWM 566), so please confirm them on [tc.canada.ca](https://tc.canada.ca) before relying on them.

---

<div align="center">

Made for apprentices working toward their licence. Keep the wrenches turning. 🔧

</div>
