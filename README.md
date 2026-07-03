# AgriLearn AI

A phone-based plant doctor for smallholder farmers in Uganda — built for **The Mastery Mentors Hackathon 2026**.

Point your camera at a sick crop leaf and get a diagnosis, a treatment plan, and the biology behind it — personalized to your exact farm, live weather, and soil, in English, Luganda, or Swahili.

## The problem

In Uganda, one agricultural extension officer is often responsible for over a thousand farmers. By the time a farmer gets expert eyes on a sick crop, the problem has frequently already spread. Most farmers, even in remote areas, now carry a basic smartphone — but nothing turns that camera into a trained first line of diagnosis and education.

## Features

- **Live camera scanner** with real-time leaf detection, not a file picker
- **On-device pixel-color analysis** — instant, offline leaf-damage measurement that cross-checks the AI diagnosis
- **My Farm profile** — district, crops, farm size, irrigation, experience, and treatment approach personalize every result
- **Live weather integration** (Open-Meteo) — real temperature, humidity, soil moisture, UV index, and ET₀ for the farmer's exact district, factored directly into disease-risk reasoning
- **Differential diagnosis** — the AI reasons through multiple candidate diagnoses and explains what it ruled out
- **AI-verified Soil Check** — confirms a photo is actually soil before analyzing it; combines AI visual analysis with the standard hand-feel "ribbon test"
- **Plant Doctor curriculum** — five structured lessons per crop with real content and multiple questions each, unlocking in sequence
- **Field Journal** — every diagnosis logged with farmer notes and follow-up status tracking (treated / resolved / recurring)
- **Multilingual output** — English, Luganda, Swahili, with voice read-aloud
- **Outbreak Map** — illustrative sample data showing what district-level early-warning detection could look like at scale

## Tech stack

- Single-file HTML/CSS/JS — no build step, no framework
- AI diagnosis and soil analysis via [Puter.js](https://puter.com) (`gemini-3.5-flash`), used client-side with no API key required
- Weather data via [Open-Meteo](https://open-meteo.com) (free, no API key required)
- Client-side computer vision: HSV color-space pixel analysis for leaf and soil damage estimation
- All personal data (farm profile, field journal, lesson progress) stored locally in the browser via `localStorage` — nothing leaves the device except the image sent for AI diagnosis

## Running it
https://agrilearnai.netlify.app/ or, 
Just open `index.html` in a modern browser — **must be served over HTTPS or from `localhost`** for the camera and weather features to work (browser security requirement for camera access). The simplest way:

1. Host it via GitHub Pages (see below), or
2. Run a local server, e.g. `python3 -m http.server` or VS Code's Live Server extension, and open via `http://localhost:...`

Opening the raw file directly (`file://`) will break the camera and weather features.

## What this honestly is (and isn't)

This is not a custom-trained image classifier — it's a general multimodal AI model reasoning against real, independently-computed signals: on-device pixel analysis and live weather data. Confidence scores below 60% are explicitly flagged rather than hidden behind false certainty. The Outbreak Map uses clearly-labeled sample data — a real shared, cross-farmer live map would require a proper backend database, which this hackathon build intentionally does not fake. It hasn't yet been validated against a labelled dataset or a trained agronomist.

## Roadmap for real deployment

- WhatsApp/SMS channel — the way information already travels for Ugandan farmers, reaching feature phones too
- Partnership with NAADS or a local agricultural NGO for validation against real diagnoses
- A dedicated backend (own API key, rate limiting, cost control) in place of the free Puter.js proxy
- A real shared database (e.g. Firebase/Supabase) so the Outbreak Map reflects live, opted-in farmer data
- Additional local languages beyond Luganda and Swahili

## License / credits

Built for The Mastery Mentors Hackathon 2026. Disease and treatment information compiled from general agricultural extension knowledge for educational use — not a substitute for professional agronomic advice.
