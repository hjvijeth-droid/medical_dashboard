# SHRIDEVI Medical Center Dashboard (Real-world ready)

This is a working hospital / medical center dashboard with real phone dialing and WhatsApp integration.

## Real patients pre-loaded
1. **Vijeth H J** — +91 73385 72879 (1st patient)
2. **Diganth A R** — +91 72048 82159

## Primary doctor
- **Dr. Meghana M** — +91 97435 82627 (General Medicine)

## What works in the real world

### Calling a patient
- Open any patient → **Call patient (normal dial)**  
  Uses the standard `tel:` link. On a phone it opens the native dialer with the number ready to call. On desktop it opens your default calling app (Skype, Phone Link, etc.).

### WhatsApp / Video call
- **WhatsApp patient** → opens WhatsApp chat with that patient.
- **WhatsApp video call patient** → opens WhatsApp with a pre-filled message. On the phone, simply tap the video camera icon inside WhatsApp to start a real video call.
- Same buttons exist for **Dr. Meghana M**.

### Live vitals (wearable band simulation)
- In **Digital health** section you will see Heart Rate and Blood Pressure updating every few seconds.
- Marked as “Live from band”. This simulates a connected smart band / BP monitor.
- Click **Sync band now** for an immediate refresh.
- True Bluetooth wearable pairing is possible later with Web Bluetooth, but support is limited; the current simulation is reliable and works everywhere.

## How to run

Requires Node 18+.

```bash
cd backend
npm install
npm start
```

Open http://localhost:3000

The server serves both the frontend and the API. Data is stored in `backend/shridevi.db`.

## Project layout
```
shridevi-dashboard/
  frontend/index.html     Full dashboard
  frontend/api-shim.js    Frontend ↔ backend bridge
  backend/server.js       Node + Express + SQLite
  backend/package.json
  database/schema.sql
```

## Notes for production use
- The `tel:` and `https://wa.me/` links are the standard, reliable way websites trigger real phone and WhatsApp actions.
- For a fully automated video call you would integrate Twilio, Agora, or WhatsApp Business API (requires business verification).
- Patient data privacy (India DPDP Act, etc.) must be reviewed before using with real medical records.
