# Application Navigation & Workable Paths 📍

Since this is a React Native Web application, you can navigate through the system using the following flow. These pages are available as routes in the web deployment.

## 🔑 Authentication Flow
- **Login Screen**: `/` (Root)
  - Purpose: Authenticate using your Email and Password.
  - Action: Enter credentials -> Redirect to Dashboard.
- **Register Screen**: `/Register`
  - Purpose: Create a new account.
  - Action: Fill details -> Tap Register -> Automatically logs in.

## 👷 Field Engineer Flow
- **Dashboard (Projects list)**: `/Dashboard`
  - Purpose: View all road projects assigned to you.
  - Action: Tap on a Project Card -> Navigate to Inspection view.
- **Inspection Detail (Segment Checklist)**: `/Inspection`
  - Purpose: See the list of road segments. Contains the "GPS Live" tracking card.
  - Action: Tap a segment to Start Inspection -> GPS card expands.
- **Inspection Form**: `/InspectionForm`
  - Purpose: Finalize the report for a specific segment.
  - Requirement: Must have 1+ image and 2+ minutes of tracking.
  - Action: Submit -> Returns to Inspection view with segment marked ✅.

## 👤 Profile & settings
- **Profile Screen**: `/Profile`
  - Purpose: View your account details and Logout.

---
**Note**: For Vercel deployment, ensure your `.env` variables are entered in the Vercel Dashboard settings for the **Backend** project.
