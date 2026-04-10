Google Workspace Android Management – Admin Cheat Sheet
1️⃣ 🔧 Prerequisite: Advanced Mobile Management

👉 You must enable this first, otherwise most controls won’t work

✔️ Why it matters
Enables full MDM control
Required for:
Work profiles
App control
Security policies
🧠 Key concept
Basic management = light control (password only)
Advanced management = full control (real MDM)
2️⃣ 🏢 Structure: Use Organizational Units (OUs)

👉 Policies are applied to OUs (like AD GPOs)

Assign settings per:
Department
Team
Device type
🔁 Important
You can:
Override settings per OU
Or let them inherit

👉 Same idea as:

AD GPO inheritance
3️⃣ 📦 Device Types (VERY important)
Type	Control Level	Notes
BYOD (personal)	Limited	Uses Work Profile
Company-owned	Full control	Can fully manage device
🧠 Key difference
Work Profile = only work data managed
Company device = full device control
4️⃣ 👤 Work Profile (Core Concept)

👉 This is the most important Android concept

✔️ What it does
Separates:
Work apps 📁
Personal apps 👤
Admin controls only work part
🔧 Options
Optional → user can skip
Enforced → required for access
Disabled → no work profile

👉 Best practice:

Enforce work profile
5️⃣ 🔐 Critical Security Settings
🔒 Auto Wipe
Wipes data if:
Device not syncing
Device non-compliant

👉 Must enable

🔑 Password / Encryption
Enforce:
Screen lock
Encryption

👉 Core compliance requirement

🚫 Block unsafe devices
Block:
Rooted devices
Non-CTS compliant devices

👉 Prevents insecure phones

6️⃣ 📲 App Control
Options:
Allow all apps ❌ (not secure)
Only allowed apps ✅ (recommended)

👉 Whitelist approach

Additional controls:
Block:
Screen capture
Data sharing to personal apps

👉 Prevent data leaks

7️⃣ 🌐 Device Restrictions

You can control:

Network settings (Wi-Fi, roaming)
Bluetooth
Factory reset
Safe mode boot

👉 Important:

Disable safe mode (bypasses policies)
8️⃣ 🔄 OS Updates
Options:
Immediate
Scheduled
Delay (up to 30 days)

👉 Best practice:

Delay updates slightly (test first)
9️⃣ 🧑‍💻 User Controls

You can restrict:

Adding accounts
Multiple users
Google account usage

👉 Prevent shadow IT

🔟 🧾 Monitoring & Visibility

Admins can see:

Installed apps
Device status
Compliance state

👉 Important for:

Audits
Troubleshooting
🚨 11️⃣ Remote Actions

You can:

Wipe device
Wipe only work profile
Lock device

👉 Critical for lost/stolen phones

🧠 Real Admin Best Practices
✔️ Minimum secure setup
Advanced management ✅
Work profile enforced ✅
Password + encryption ✅
Auto wipe ✅
Block rooted devices ✅
App whitelist ✅
✔️ Recommended architecture
Users → OU → Android policies → Devices
⚠️ Common mistakes
❌ Not enabling advanced management
❌ Allowing all apps
❌ Not enforcing work profile
❌ Ignoring compliance rules
❌ Letting users factory reset unmanaged
🧠 One-line summary

👉 Think of it like:

Google Workspace Android = "GPOs for phones"
OUs = scope
Policies = GPOs
Work profile = sandbox
Compliance = enforcement
