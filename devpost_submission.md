# Devpost Submission — Copy/Paste Material

## Title
AgriLearn AI — A Plant Doctor for Farmers Who Don't Have One

## Tagline / short description
Point your phone at a sick crop leaf and get a diagnosis, a treatment plan, and the biology behind it — personalized to your exact farm, weather, and soil, in English, Luganda, or Swahili.

## Full description

**The problem**

In Uganda, one agricultural extension officer is often responsible for over a thousand farmers. By the time a farmer gets expert eyes on a sick crop, the problem has frequently already spread. Most farmers, even in remote areas, now carry a basic smartphone — but nothing turns that camera into a trained first line of diagnosis and education.

**What we built**

AgriLearn AI turns a phone into a personalized agricultural diagnosis and education tool for cassava, maize, banana, and coffee farmers.

- **A live camera scanner** — not a file picker — detects a leaf in real time before capture.
- **Instant, on-device pixel-color analysis** measures visible leaf damage before any AI call is made, and is fed back into the diagnosis as a cross-check.
- **A real "My Farm" profile** — district, crops, farm size, irrigation access, farming experience, and treatment approach — personalizes every result instead of giving generic advice.
- **Live weather integration** pulls real current conditions (temperature, humidity, soil moisture, UV index, and more) for the farmer's exact district and factors them directly into disease-risk reasoning.
- **Genuine differential diagnosis** — the AI reasons through 2–3 candidate diagnoses and explains what it ruled out, the way a real plant pathologist would, rather than presenting a single guess as fact.
- **AI-verified Soil Check** — checks that a photo actually shows soil before analyzing it, combines a real AI visual read with the standard hand-feel "ribbon test," and is personalized with the same farm and weather context.
- **A real Plant Doctor curriculum** — five structured lessons per crop, each with real content and multiple comprehension questions, unlocking in sequence — not a single flat quiz.
- **A Field Journal with outcome tracking** — every diagnosis is logged with farmer-editable notes and a follow-up status (treated, resolved, recurring), building a real farmer-confirmed accuracy record over time.
- **Multilingual output** — English, Luganda, and Swahili, with voice read-aloud for low-literacy users.
- **An illustrative Outbreak Map** — sample data, clearly labeled as such, showing what district-level early disease-outbreak detection could look like if built on this same logging architecture at scale.

**Our engineering approach**

Rather than training a narrow image classifier limited to a fixed disease list, we built AgriLearn on a multimodal reasoning model cross-checked against two independent signals we compute ourselves: on-device pixel-color analysis and live weather data for the farmer's exact location. This gives the system far broader diagnostic range than a small custom-trained model could achieve in this timeframe, while the independent cross-checks keep it calibrated — confidence scores below 60% are explicitly flagged as "see a human expert" rather than smoothed over. The soil analysis runs the same verified-AI pipeline as leaf diagnosis, and the outbreak map is intentionally built on sample data and labeled as such — it demonstrates the exact logging architecture a real cross-farmer deployment would use, without pretending to be live before it has real users. The next milestone on our roadmap is formal validation against a labelled dataset and review by a trained agronomist.

**What real deployment would need next**

A WhatsApp or SMS channel (since that's how information already travels for Ugandan farmers), partnership with NAADS or a local agricultural NGO for validation, a real backend in place of the free AI proxy used for this build, and a genuinely shared, cross-farmer database to make the outbreak map live rather than illustrative.

## "How it relates to education" field

AgriLearn's core design principle is teaching the biology of plant disease, not just naming it. Every diagnosis includes a plain-language explanation of how the specific pathogen or pest attacks the plant and why the visible symptoms appear, plus genuine differential reasoning showing what else was considered — turning a "what's wrong with my plant" lookup into an actual lesson in plant pathology. Beyond individual diagnoses, every crop has a real five-lesson curriculum with multiple comprehension questions per lesson, unlocking sequentially like an actual course — not a single flat quiz. The offline Learn Library and Soil Check extend this into a standalone reference on plant pathology and basic soil science that works with zero internet connection, and the Field Journal's follow-up tracking turns each diagnosis into a longitudinal learning record rather than a one-off answer.

## Instructions for accessing / running the project

1. Open the live link: **[paste your GitHub Pages URL here once set up]**
2. Grant camera permission when prompted (needed for the live leaf scanner)
3. Set up "My Farm" on first visit (district + crops) to unlock personalized weather and diagnosis
4. Try Diagnose, Soil Check, Learn Library, Field Journal, Outbreak Map, and About from the top navigation

No installation required — works in any modern mobile or desktop browser with an internet connection (needed for AI diagnosis and weather; Learn Library and Field Journal work offline once loaded).

## Source code
**[paste your GitHub repo URL here]**
