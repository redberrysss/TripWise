# TripWise

An offline-first Kotlin travel planner. Compose/Material 3 UI, Room + Flow repository design, Navigation Compose dependencies, DataStore-ready preferences and a Retrofit-ready API boundary are included.

## Portfolio features

- Seeded upcoming and previous trips with budget, duration, destinations, and activities.
- Add an expense, categorise it and see remaining budget; itinerary activities are shown by day.
- Offline data stays available after restart through Room. Discovery/weather intentionally shows an explicit offline/API-not-configured state: no live responses are fabricated. Maps have a coordinate/address fallback until a map key is supplied.

## Database & architecture

Room stores `Trip`, `PlanItem`, and `Expense`; a repository exposes Flow, and `TripViewModel` supplies immutable UI state to composables. This is designed to add real Retrofit services through `data/remote` without exposing secrets.

## Setup / test

Open this directory in Android Studio with JDK 17+ and run `app`. Terminal checks: `./gradlew assembleDebug test lint`. Add API secrets only through untracked `local.properties` or environment/CI secrets. Future work: destination search, authenticated cloud sync and configured Maps SDK.

## Screenshots

Capture the Trips, Plan, and Budget tabs after launching the seeded demo and add them under `docs/screenshots/`.
