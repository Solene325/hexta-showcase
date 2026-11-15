# HEXTA · Crew health for long missions

Project page of **HEXTA**, by team **Synergy 5** (École Centrale Casablanca) for the **NASA Space Apps Challenge 2026**, challenge *Create health monitoring software for astronauts on space missions*.

**Live page:** https://solene325.github.io/hexta-showcase/

## The problem

Halfway to Mars, nobody on board is a doctor. A message to Earth can take up to about 20 minutes each way, with longer blackouts, so help has to start on board. Astronauts sleep about 6 hours a night on ISS missions, and the five NASA hazards of human spaceflight leave traces in the body every day.

## Our solution

HEXTA is one traceable loop, from a morning check-in to the ground:

1. **Remind**: a daily check-in task at 07:00 mission time, with a 30-minute snooze.
2. **Check in**: sleep and sleepiness in under five minutes, plus mood, symptoms and optional readings.
3. **Explain**: every reading keeps its unit, method and quality; transparent rules flag three short nights in a row or a value past a reference threshold, with the evidence.
4. **Review**: the crew medical officer works from one console with motivated states, trends, lab results and follow-up requests.
5. **Report**: a frozen individual report is queued for the ground and keeps the same ID until a receiver acknowledges it.

Crew members can also photograph a skin finding or a urine sample, or measure their pulse with the laptop camera (computed on the server from the colour of the face, no video sent). Claude Vision describes what it sees and cites the knowledge base; server rules keep it from naming a diagnosis and can only raise an alert. Radiation exposure is followed through module dosimeter readings (µGy/h, with sensor and location).

## NASA data and stack

- **NASA OSDR, Inspiration4 crew**: 7,768 real astronaut measurements from OSD-569 (complete blood count), OSD-575 (metabolic panel, cytokines) and OSD-656 (urine inflammation). CC0 1.0, DOI 10.26030/e0rx-sh52. Shown as historical context, never mixed with the simulated crew series.
- **NASA Human Research Program**: the five hazards and their risks structure the body map and indicator cards.
- **NASA-STD-3001**: cabin CO₂ and career radiation dose limits.
- **Stack**: Laravel 13 API, MongoDB Atlas (documents, GridFS, Atlas Search), Claude Vision, Three.js, offline-first web app, automated test suite.

## Impact

The crew keeps a five-minute routine and knows a worry reaches someone, even without signal. The crew medical officer sees who needs attention and why. The ground receives complete reports with receipts. On Earth, the same loop fits polar stations, ships and remote villages.

HEXTA is a prototype with simulated crew data. It is not a medical device: it does not diagnose or prescribe, and real thresholds would need a validated mission medical policy.

## View the page

Open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8090
```

then visit http://localhost:8090. The 3D model is bundled in `assets/hexta-body.glb.js`, so the page also works when opened directly from disk.

## Credits

- Photographs: NASA Image and Video Library. HEXTA is not affiliated with or endorsed by NASA.
- 3D anatomy model: Innerscene, public domain (CC0 1.0).
- Three.js (MIT). Fonts: Young Serif and Figtree (SIL Open Font License).
- Full list of scientific sources in the *Sources* section of the page.

© 2026 Synergy 5, École Centrale Casablanca.
