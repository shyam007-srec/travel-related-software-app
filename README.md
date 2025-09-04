# Project Phases and Roadmap

## 🔑 Phase 1: Foundation & Setup
**Goal:** Get a skeleton system ready (app + backend + DB).  
- Team alignment & roles  
  - Mobile dev (Flutter/React Native)  
  - Backend dev (FastAPI/Node)  
  - Data/algorithms (trip detection)  
  - UI/UX (nudge flows, consent screens)  
- Decide stack  
  - Mobile: Flutter (cross-platform, faster)  
  - Backend: FastAPI (Python) → easy, integrates ML later  
  - DB: PostgreSQL + PostGIS (spatial queries, OD maps)  
  - Portal: React + Leaflet (quick charts + maps)  
- Repo setup  
  - GitHub/Bitbucket + CI/CD  
  - Project boards (Trello/Jira) → tasks  
- Backend setup  
  - Install FastAPI + Postgres locally  
  - Define API endpoints (`/consent`, `/trips`, `/users`)  
  - Create DB schema (users, trips, points, companions)  
✅ **Deliverable:** empty mobile app → consent screen → POST test data to backend → stored in DB.

## 🔑 Phase 2: Mobile App Core
**Goal:** Detect movement + basic trip storage.  
- Permissions & consent  
  - Location (foreground + background)  
  - Activity recognition (walking, vehicle, cycling)  
  - Battery optimization bypass (for Android)  
- Background tracking  
  - Capture location every few minutes (when moving)  
  - Store locally (SQLite)  
- Trip detection (basic)  
  - Start trip: moving > 2 min  
  - End trip: still > 5 min  
  - Save trip \{start_time, end_time, origin, destination\}  
✅ **Deliverable:** app auto-detects trips & saves to phone.

## 🔑 Phase 3: User Interaction (Nudges)
**Goal:** Enrich raw trips with human input.  
- Trip review UI  
  - Timeline view: today’s trips  
  - Nudge: “Trip detected → Confirm/Edit”  
- Mode detection  
  - Rule-based from speed & activity  
  - User can override in 1 tap  
- Companions prompt  
  - “Were you alone?” → Yes/No  
  - If No → add number of adults/children  
- Purpose prompt (Work, School, Shopping, Other)  
✅ **Deliverable:** user sees trips, edits details, trips synced to backend.

## 🔑 Phase 4: Backend & Data Handling
**Goal:** NATPAC scientists can see aggregated trip data.  
- API hardening  
  - Auth: device token  
  - Validation (trip duration > 2 min, distance > 200m)  
- Data model finalization  
  - trips, points, companions, users, consents  
- PostGIS for spatial queries  
- Analytics pipeline  
  - Scripts to calculate trip lengths, OD matrix, mode shares  
✅ **Deliverable:** server stores valid trips, researchers can query/export.

## 🔑 Phase 5: Scientist Portal
**Goal:** Dashboard to explore & download.  
- Web dashboard  
  - Trips/day (line chart)  
  - Mode share (pie)  
  - Map visualization (origins/destinations, OD heatmap)  
- Filters  
  - Date range  
  - Mode  
  - City/region (map box filter)  
- Data export  
  - CSV download  
✅ **Deliverable:** NATPAC scientist logs in → sees aggregated OD & trips.

## 🔑 Phase 6: Testing & Iteration
**Goal:** Make it usable & reliable.  
- Field testing  
  - 5–10 people use app for 2–3 days  
  - Validate trips vs ground truth  
- Battery optimization  
  - Ensure background tracking doesn’t drain phone  
  - Adjust location sampling (low-power first, GPS only in motion)  
- Privacy compliance  
  - Data anonymization  
  - Delete data option  
  - Opt-out anytime  
✅ **Deliverable:** working beta app tested with small group.

## 🔑 Phase 7: Completion (Production-ready)
**Goal:** Ready for wider NATPAC pilot.  
- App release  
  - Publish on Google Play (internal testing track)  
  - Distribute APK for testing  
- Scalability  
  - Deploy backend on cloud (AWS/GCP/Azure)  
  - Secure DB access  
  - Monitoring (logs, crash reports)  
- Documentation  
  - User manual  
  - Scientist portal manual  
  - Data dictionary (trip fields, meaning)  
✅ **Deliverable:** NATPAC has a mobile app + backend + portal ready for pilot survey.

---

## 🚀 Final Hackathon/Project Storyline
**Problem:** Manual surveys are slow + limited  
**Innovation:** Mobile app auto-captures trips + nudges user for missing details  
**Solution:** App + backend + scientist portal  
**Impact:** Scalable, real-time, accurate data → better transport planning  
