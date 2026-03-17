# RoadQuality (Pravi Road QC) 🛣️✅

RoadQuality is a comprehensive **Smart Road Inspection & Quality Control System** designed to streamline the project management of road construction and maintenance. It empowers field engineers to conduct rigorous on-site inspections while providing administrators with real-time tracking, data validation, and automated quality alerts.

## 🚀 Key Features

### 👷‍♂️ Field Engineer Module
- **Live GPS Tracking**: Continuous geo-logging during inspections with polyline path history.
- **Anti-Cheat Logic**: Native detection and rejection of "Mock Locations" (Mock GPS apps).
- **Road Segmentation**: Large projects are divided into manageable segments with independent statuses (Not Visited, In Progress, Completed).
- **Mandatory Media Capture**: Forces engineers to take live photos/videos for each segment (Gallery uploads are disabled).
- **Geotagged Watermarking**: Automatically overlays GPS coordinates and timestamps onto captured media previews.
- **Structured Inspection Forms**: Eliminates free-text manipulation. Engineers select from predefined material quality cards and defect chips (Potholes, Rutting, Cracks, etc.).
- **Time Constraints**: Prevents "speed-running" inspections; submission is locked until a minimum inspection time has elapsed.

### 🛡️ Admin Dashboard (Work in Progress)
- **Real-Time Map View**: Monitor engineers' live locations via Socket.IO.
- **Project Progress Monitoring**: Visual breakdown of segment completions across all active projects.
- **Quality Alerts**: Automatic flagging of segments reported with poor material quality or excessive defects.

## 🛠️ Technical Approach

### 🏗️ Tech Stack
- **Frontend**: React Native (Expo) - Cross-platform (Android, iOS, Web).
- **Backend**: Node.js & Express.
- **Real-time**: Socket.IO for live location broadcasting.
- **Database**: MongoDB (Atlas) for persistent storage.
- **Cloud Storage**: Cloudinary for geotagged media uploads.
- **Authentication**: JWT-based session management.

### 🔄 Project Workflow
1. **Assignment**: Admin creates a project in MongoDB and assigns a Field Engineer.
2. **Execution**: The Field Engineer opens the app, selects an assigned project, and chooses a road segment to inspect.
3. **Tracking**: The app starts a tracking session, logging GPS coordinates and ensuring the engineer is physically present.
4. **Evidence Collection**: The engineer captures photos of the road work. The system embeds real-time metadata.
5. **Report Submission**: The engineer fills out the structured quality form. The system validates the time spent and the presence of media before allowing submission.
6. **Sync**: Data is synced to the central database, and Socket.IO pushes updates to the admin dashboard for real-time visibility.

## ⚙️ Setup & Installation

### Backend
1. `cd backend`
2. `npm install`
3. Create `.env` file with:
   ```env
   MONGO_URI=your_mongodb_uri
   JWT_SECRET=your_secret
   CLOUDINARY_CLOUD_NAME=name
   CLOUDINARY_API_KEY=key
   CLOUDINARY_API_SECRET=secret
   ```
4. `npm start`

### Mobile (Web/Android/iOS)
1. `cd mobile`
2. `npm install`
3. Update `src/constants/index.js` with your Local IP address.
4. `npx expo start` (Press `w` for Web preview)

## 🏁 Deployment
This project is configured for deployment on:
- **Backend**: Vercel (using serverless functions).
- **Frontend**: Expo Web (Vercel/Netlify).

---
Developed for **Pravi Road QC** to ensure every road built meets the highest standards.
