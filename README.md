# SafeHer+ – Women's Safety Android App (Java + XML + SQLite)

## Open & run
1. Android Studio (Koala / 2024.1+ or newer) → **File ▸ Open** → select the `SafeHerPlus` folder → let Gradle sync (it downloads Gradle 8.7 / AGP 8.5.2).
2. Run on an emulator (use a **Google APIs / Play** image, API 26+) or a real phone.
3. First launch: Splash → Onboarding → Sign Up (set a **4-digit Safety PIN**) → Home.

## Emulator tips
- Location: ⋯ Extended controls ▸ Location ▸ set a point ▸ Send (GPS is empty by default).
- SMS: Extended controls ▸ Phone ▸ SMS shows messages sent to emulator numbers (e.g. 5554). Add a contact with number `5554` to test SOS.
- Camera: Extended controls ▸ Camera (virtual scene) is used for journey / SOS photos.
- Nearby Places needs internet (OpenStreetMap tiles + Overpass API).

## Real vs simulated
| Feature | Status |
|---|---|
| GPS, camera (photos only, no video), microphone, notifications, SMS, call/map intents | REAL |
| Nearby hospitals/police/pharmacies/bus/metro | REAL (OpenStreetMap Overpass) |
| SQLite storage, salted-hash passwords & PIN, App Lock, Dark Mode | REAL |
| Journey photo timeline, check-ins, escalation SMS | REAL (foreground service) |
| "Continue with Google" | SIMULATED (local demo account) |
| Report status Pending → Under Review (2 min) → Resolved (10 min) | SIMULATED (no backend) |
| Community incident map data | SIMULATED around your location (+ your own reports, anonymised) |
| Safe-route suggestion (in infographic) | NOT implemented |

## Structure
`ui/` activities & fragments · `db/DatabaseHelper` (all tables) · `model/` · `service/JourneyService` · `util/` helpers
