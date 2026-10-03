# Gamma prompt: EVP proposal defense (exactly 10 cards)

10 Gamma cards + your existing title and closing slides = 12 slides total (within the 13/14 limit, with 1 to 2 spare).

Order: Problem, Introduction, Solution, Literature summary, Base papers (1 card), Limitations, Proposed solution, Architecture, SDGs, Contributions and timeline.

## Settings
- Paste in text > Presentation > 16:9
- Text mode: Preserve
- Cards: 10
- Language: English (UK)
- Images: no AI images
- Theme: clean light theme; brand colours navy 14213D, green 17875B, red D62839, amber F2A300, background F3F5F9

## Box A: Additional instructions
```
Create exactly 10 cards, one per block separated by ---, in the given order. No title, agenda, thank-you or references card. Do not add any text. Keep the text as is: do not rewrite, shorten or invent; keep all numbers, units and reference tags such as [12].

Audience: university faculty panel, final year project proposal defense. Tone: academic, precise. UK English.

Style: 16:9, uncluttered. Light background F3F5F9, white rounded cards, soft shadow; card 1 dark navy 14213D with white text. Navy dominant; green 17875B = proposed/benefit; red D62839 = problem/limitation; amber F2A300 = accent. Serif headings, sans body, left-aligned, high contrast. Small spaced-caps label above each title. No stock photos or AI images, no emoji; use icons in coloured circles and big-number callouts. Each card fits one screen; body text at least 14pt, tables at least 12pt.

Layouts:
1 Statement very large, "no low-cost, vehicle-independent way" and "avoidable delays" in amber; three stat cards below.
2 Left: three icon rows and a green question box. Right: two stacked red stat cards.
3 Left: large statement card with an amber trade-off box. Right: three stacked big-number cards.
4 One four-column table, six rows tinted by family (blue camera, green benchmarks, amber acoustic), legend below.
5 One full-width table, six rows tinted by the same families; the "Limitations" column text in red; footnote below.
6 Six numbered cards (2x3), red numbers, navy banner below.
7 Row of five step cards joined by arrows; below, a 4-bar column chart (3.6 s red, 7.2 s amber, 10.8 s green, 14.4 s green) and a light-green scope card.
8 Two horizontal flows of five boxes joined by arrows; top lane light red, bottom lane light green; dashed green outline labelled FOCUS AREA around boxes 2 to 4.
9 Three equal cards, SDG 3 first and tagged "Closest fit"; each has a numbered badge only (3 green 4C9F38, 11 amber FD9D24, 9 orange F36D25), the target in bold, the contribution below. Do not use official UN SDG icons.
10 Left: six numbered contribution cards and a note. Right: Gantt chart, 11 bars on an 18-week axis (fallback: table). Strip of four target chips along the bottom.
```

## Box B: Text to paste
```
PROBLEM STATEMENT
# The Problem in One Sentence

Pakistani cities have no low-cost, vehicle-independent way of giving emergency vehicles priority at signalised intersections, and time-critical emergencies suffer avoidable delays as a result.

**+5%**: odds of on-scene death for each extra minute of EMS response, Punjab Rescue 1122 data [3]
**30.9%**: of 978 Karachi trauma patients reached the emergency room within an hour [4]
**Sec. 112AA**: right of way applies only while an ambulance or fire truck is signalling (PMVO 1965, ICT) [10]

---

INTRODUCTION
# Emergency Vehicles Lose Minutes at Pakistan's Signals

**Signals ignore emergencies**
Signals in Lahore, Karachi and Islamabad run fixed-time or locally adaptive cycles with no link to emergency services. Ambulances rely on siren, horn and driver nerve.

**EVP is solved abroad, not here**
Opticom and NTCIP 1211 priority control are installed in many countries [1]. We found no equivalent at a signalised intersection in Pakistan.

**Every EVP product needs vehicle hardware**
IR emitters, RF transponders and GPS/GSM trackers are hard to roll out across government, charity and private fleets.

THE QUESTION
Can an intersection-side, camera-only system detect an approaching ambulance or fire truck and grant it priority, at low cost and with nothing on the vehicle?

**~20%**: of the Lahore study area that fire-brigade vehicles can reach within a 7-minute window [8]
**~7 min**: average Rescue 1122 response time, across about 2.5 million emergencies attended in 2025 [6], [7]

---

SOLUTION STATEMENT
# The Solution in One Sentence

A camera-only, intersection-side EVP system that detects an approaching ambulance or fire truck with Computer Vision alone and grants it a green, with nothing on the vehicle.

THE TRADE-OFF WE ACCEPT
A shorter detection range than GPS and some vulnerability to heavy rain, fog and very low light. The simulation models these as reduced detection probability and range; real values are measured on hardware later.

**0**: pieces of equipment on any vehicle
**0**: GPS, GSM or cellular dependency; each intersection works alone
**PKR 0**: recurring per-vehicle cost, versus about PKR 2,250 per vehicle for GPS/GSM

---

LITERATURE REVIEW | SUMMARY
# Base Papers at a Glance: Title, Year and Dataset

| Ref | Title | Year | Dataset |
|---|---|---|---|
| [11] | IoT Based Emergency Vehicle Detection using YOLOv8 (Suhana et al., JAMRIS) | 2025 | Camera feed from a busy road (name and size not stated) |
| [12] | Intelligent Traffic Light Control System for Emergency Vehicles Using Deep Learning and Signal Synchronization (ResearchGate) | 2025 | "Curated dataset" (not named in the abstract) |
| [13] | Object Detection for Vehicles with YOLO (Maleki et al., IEEE SAMI) | 2024 | Vehicle Dataset: 29,759 images, 7 classes incl. ambulance and fire truck |
| [19] | Performance Analysis of YOLO-based Architectures for Vehicle Detection from Traffic Images in Bangladesh (Alamgir et al., ICCIT) | 2022 | 7,390 images, 21 vehicle types (DhakaAI + Poribohon-BD + self-collected) |
| [14] | Acoustic-Based Emergency Vehicle Detection Using Convolutional Neural Networks (Tran and Tsai, IEEE Access) | 2020 | Authors' siren / horn / noise dataset (size not in abstract) |
| [15] | From Large-scale Audio Tagging to Real-Time Explainable Emergency Vehicle Sirens Detection (Giacomelli et al., arXiv) | 2025 | AudioSet EV subset (author-built) + reference datasets |

Camera-based EVP prototypes: [11], [12] | Detector benchmarks and datasets: [13], [19] | Acoustic siren detection: [14], [15]

---

LITERATURE REVIEW | BASE PAPERS
# Base Papers Explained: Contribution, Limitations and Path Forward

| Paper | Setup and contribution | Limitations | Future path and our takeaway |
|---|---|---|---|
| [11] IoT YOLOv8 detector (2025) | YOLOv8 on Raspberry Pi with Pi Camera; 31 FPS, 95% accuracy; alerts to emergency services | Dataset unnamed; accuracy only; no signal control, lead time or fail-safe | Authors: advanced ML and extra sensors. Ours: add placement, gating, preemption and fail-safe |
| [12] Signal control and synchronisation (2025) | CNN detector (YOLO on Pi 5 per our reading) plus timing from speed limits and traffic density; 97.0% accuracy; automatic green across junctions | Dataset unnamed; abstract silent on lead time, false triggers and fail-safe | Authors: not stated. Ours: keep intersections independent; add fail-safe and latency analysis |
| [13] Vehicle Dataset and YOLO benchmark (2024) | 29,759 images, 7 classes incl. ambulance and fire truck; YOLOv7 best: 85% precision, 85% mAP@0.5 | Web-sourced, not Pakistani; detection only; YOLOv8 not evaluated | Authors: not stated. Ours: Stage-1 dataset and baseline for YOLOv8n |
| [19] YOLO for Bangladeshi traffic (2022) | 7,390 images, 21 vehicle types; YOLOv5x best: mAP +7% over YOLOv3, +4% over YOLOv5s | General detection; FPS and edge feasibility not reported | Authors: not stated. Ours: precedent for Stage 2 (150-300 local images plus augmentation) |
| [14] SirenNet (2020) | WaveNet on raw audio + MLNet on MFCC / log-mel; 98.24% accuracy, 96.89% on 0.25 s clips | Alerts drivers only; no Pakistani sirens; dataset size not stated | Authors: drivers and autopilot. Ours: audio as a future second channel |
| [15] E2PANNs (2025) | Lightweight CNN for binary siren detection; AudioSet EV subset; real-time on edge; explainable | Siren vs not only; metrics not in abstract; no Pakistani sirens | Authors: not stated. Ours: optional microphone cross-check, future work |

Details come from the published abstracts; limitations are what the abstracts do not report.

---

LITERATURE REVIEW | OVERALL LIMITATIONS
# What Existing Work Does Not Solve for Pakistan

1. **On-vehicle hardware dependence**
IR, RF and GPS/GSM EVP need a unit on every emergency vehicle (about PKR 2,250 per GPS+GSM unit) and coordination across independent fleets. [1]

2. **Positioning and network fragility**
GPS drift and multipath error in dense urban corridors; a live cellular link adds a failure point. IR is line-of-sight only.

3. **Camera prototypes stop at detection**
Their abstracts report no camera lead time, false-trigger handling or fail-safe reversion. [11], [12]

4. **No Pakistani emergency-vehicle data**
Benchmarks are web-sourced or Bangladeshi. Pakistani sets cover make-and-model, not ambulances or fire trucks. [13], [16], [17], [19]

5. **Benchmarks, not system validation**
Accuracy and mAP are reported, not latency to green, cross-traffic delay or a no-preemption baseline. [13], [14], [15], [19]

6. **Not designed for Pakistan's context**
No reviewed work targets Pakistani liveries, intersections, mixed fleets or the Section 112AA right-of-way rule. [10]

THE OPEN GAP: a vehicle-independent, camera-only, fail-safe EVP, validated against explicit targets, for Pakistani conditions.

---

PROPOSED SOLUTION
# Detect, Track, Trigger, Preempt, Revert

**1. Detect** (MODULE 2)
YOLOv8n fine-tuned on public emergency-vehicle datasets; benchmark yields a detector-performance profile

**2. Track and gate** (MODULE 3)
Centroid / IoU tracker; act only after a high-confidence detection holds over several frames

**3. Trigger policy** (MODULE 5)
Request only for vehicles with active warning devices (Sec. 112AA); look-alikes rejected

**4. Preempt** (MODULE 4)
Yellow and all-red clearance, then green for the emergency approach; cross-traffic held

**5. Revert and fail-safe** (MODULES 3, 4)
Normal cycle within 2 s of the exit zone; falls back on camera loss or timeout

**Why the camera sits 150-200 m upstream**
Warning time at 50 km/h (13.9 m/s), in seconds: 50 m = 3.6 | 100 m = 7.2 | 150 m = 10.8 | 200 m = 14.4
Target: first sustained detection to green in under 3 s, leaving time for cross-traffic clearance.

**Scope: simulation first**
SUMO model of one representative signalised intersection; Python controller via TraCI; repeated random seeds against a no-preemption baseline. Hardware (Raspberry Pi 4, relay-driven signal heads) is future work.

---

ARCHITECTURE
# Current vs Proposed Architecture: Our Focus Area

CURRENT: GPS / IoT, IR and RF EVP
Vehicle-side unit: IR emitter, RF transmitter or GPS+GSM
-> Link: line-of-sight, RF channel or cellular
-> Receiver or central platform: computes vehicle proximity
-> Signal controller: priority request (NTCIP 1211 model)
-> Signal heads: green for the vehicle
Problems: hardware on every vehicle | needs a live link | central server or fleet coordination

PROPOSED: Camera-only Computer Vision EVP
Upstream camera: 150-200 m before the stop line (simulated)
-> YOLOv8n detector: fine-tuned on public data; performance profile
-> Tracker, gating, trigger: multi-frame confidence, exit zone, warning-device rule
-> Signal controller: Normal / Preempt / Revert / Fail-safe via TraCI
-> Signal heads: green for the emergency approach (SUMO)
FOCUS AREA: designed, simulated and validated in SUMO (detector, tracker and trigger, signal controller)
Benefits: nothing on the vehicle | no GPS, no network | each intersection independent

---

SUSTAINABLE DEVELOPMENT GOALS
# Alignment with the UN Sustainable Development Goals

The closest fit is SDG 3, since the whole point of the system is to cut emergency response times.

**SDG 3: Good Health and Well-being** (Closest fit)
Target 3.6: reduce road traffic deaths and injuries.
Removes delay at intersections for ambulances and fire trucks, supporting faster response to crashes and time-critical medical emergencies.

**SDG 11: Sustainable Cities and Communities**
Target 11.2: safe and sustainable transport systems.
Makes signalised intersections more responsive to emergency traffic at low cost, deployable one intersection at a time with no equipment on vehicles.

**SDG 9: Industry, Innovation and Infrastructure**
Target 9.1: reliable and resilient infrastructure.
Delivers smart-infrastructure capability from commodity hardware and open-source software that can be built and maintained locally. [22]

---

CONTRIBUTIONS AND PROPOSED TIMELINE
# What We Contribute and When

CONTRIBUTIONS
1. Two-stage data: public datasets now, Pakistani liveries later
2. Camera-placement and lead-time study
3. Multi-frame gating with exit-zone tracking
4. Fail-safe controller; independent intersections
5. Trigger tied to active warning devices (Sec. 112AA)
6. SUMO validation against targets and a no-preemption baseline
Note: YOLOv8 is used as it comes. The contribution is the integrated design, validated in simulation.

PROPOSED TIMELINE (18 WEEKS)
Phase 1. Literature review and requirements: weeks 1-2
Phase 2. Simulation environment setup: weeks 2-3
Phase 3. Baseline model fine-tuning (public datasets): weeks 3-5
Phase 4. Detector performance characterisation: weeks 5-7
Phase 5. Vehicle tracking and reversion logic: weeks 8-9
Phase 6. Simulated signal controller integration: weeks 8-10
Phase 7. Camera placement and lead-time analysis: weeks 10-11
Phase 8. Trigger policy and scenario design: weeks 11-12
Phase 9. System integration and SUMO experiments: weeks 13-14
Phase 10. Analysis and benchmarking: weeks 15-16
Phase 11. Documentation and final defence preparation: weeks 17-18

PROVISIONAL TARGETS (measured in SUMO against a no-preemption baseline)
Preemption accuracy >95% | Latency <3 s | False-trigger rate <2% | Reversion within 2 s
Hardware deployment and local data collection are future work.
```

## After generating
1. Outline shows exactly 10 cards, no title or closing card.
2. Spot-check: 97.0%, 98.24%, 96.89%, 7,390, 29,759, PKR 2,250, chart values 3.6 / 7.2 / 10.8 / 14.4 s, SDG numbers 3, 11, 9, and the 11 timeline week ranges.
3. If a card is reworded: regenerate it with "Restore the original text exactly."
4. Export: Share > Export > PowerPoint. Then add your existing title and closing slides (12 total).
