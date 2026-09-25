# Selah Events Android Updates

This repository is the public Android update channel for Selah Events Management Services.

## Responsibilities
- **Supabase** is the live shared data source for bookings, planner records, staff profiles, and permissions.
- **GitHub Releases** distributes signed Android APK updates.
- **latest.json** must point only to an APK that already exists as a signed GitHub Release asset.

## Current sync architecture
Selah App 1.4.1 uses the same Supabase project on Windows and Android. Local changes are pushed to `public.selah_cloud_records`; Supabase Realtime signals other signed-in devices to re-fetch the canonical records. A periodic polling fallback remains enabled so missed WebSocket messages cannot leave devices permanently out of sync.

## Release rule
Do not advance `latest.json` until the signed APK for that version has been published. This prevents users from receiving a broken update link.
