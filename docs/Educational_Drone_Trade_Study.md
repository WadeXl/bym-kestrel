# Trade Study: What Makes a Good Educational Drone Platform?

**BYM: Kestrel program. Rev A, 2026-11-09.** A desk study: prices and specs come from vendor pages and listings checked on this date. Scores are engineering judgment, not measurements. **The Kestrel K1 is scored on its projected design; it has not been built.**

---

## 1. Question and bottom line

**Question:** What should BYM optimize for in a drone that 5th–6th graders build and fly, and that high schoolers later program for autonomy? How do today's platforms, and the Kestrel K1 v1 design, measure up?

**Bottom line:**
1. **Seven traits make a good educational drone**, listed here by weight in BYM's case:
   - **Safe enough that a teacher says yes.**
   - **Holds position by itself indoors.** This is what turns flying into programming.
   - **A programming ladder with no dead end** (blocks → text → onboard code).
   - **Survives crashes cheaply.**
   - **Affordable** once you count spares and batteries.
   - **Real build value.**
   - **A low setup burden for teachers.**

   Two quieter traits decide whether a program *lasts*:
   - **Vendor longevity.** The Tello's discontinuation stranded classrooms.
   - **Openness**, so you can repair, re-source and extend it.
2. **No platform wins everything.** Under BYM's baseline weights, the top four are within 0.15 points of each other, which is effectively a tie: Crazyflie 2.1+, CoDrone EDU, Crazyflie Brushless and Kestrel K1. The ranking depends on the weighting:

   | Emphasis | Leader |
   |---|---|
   | Middle-school build | **Kestrel K1** |
   | High-school autonomy | **Crazyflie** |
   | Budget-first | **CoDrone EDU** |

3. **Kestrel's reason to exist is build value + openness + growth room.** Its two weaknesses are **cost** ($485–715 per kit vs $249 for CoDrone EDU) and **teacher/volunteer setup burden** (pre-kitting, ArduPilot configuration). Fixing just those two (≤ $400/kit, plus a one-click web configurator) moves Kestrel to **first under the BYM baseline and middle-school-build weightings**. It would still trail Crazyflie for high-school autonomy and CoDrone on a pure budget basis (§6).
4. **Recommendation:** keep developing Kestrel, with **Rev B goals set by this study**: cost ≤ $400/kit, a "BYM Configurator" in the web app, and ≤ 200 g. Meanwhile, **buy one CoDrone EDU and one Crazyflie 2.1+ STEM bundle** as benchmarks. They let you run programming lessons now and give the Kestrel a yardstick to beat.

---

## 2. Method

1. **Criteria** come from your stated goals for the BYM kit, plus the K-12 drone-education literature. That literature is thin: Slater (2024) notes there is little empirical research guiding drone-curriculum developers. The recurring themes are teacher readiness, **cost and sustainability** as the main adoption barriers, and five common entry pathways (racing, precision obstacle courses, coding, videography, rules/ethics).
2. **Gates (pass/fail) come before scoring.** A platform must:
   - fly indoors,
   - be safe for ages 10–12 with adult supervision,
   - and be buyable or buildable in 2026. Tello EDU fails this gate. It is kept only as a historical baseline.
3. **Scoring:** 11 weighted criteria, each scored 1–5 (§3). Weighted score = Σ(weight × score) / 100.
4. **Sensitivity:** the scores are re-ranked under 4 weight profiles to see which conclusions are robust.

---

## 3. Criteria (what "good" means)

| # | Criterion | BYM weight | Scores 5 when… | Scores 1 when… | How to measure |
|---|---|---|---|---|---|
| C1 | **Safety** | 15 | Light (< 60 g) or fully enclosed props; low pack energy; physical kill/arm; failsafe lands | Exposed props on a > 250 g craft; no kill switch | Mass, prop exposure, pack Wh, failsafe tests |
| C2 | **Build value** | 10 | Students meaningfully assemble frame, propulsion and electronics, without soldering | Ready-to-fly box | Count student assembly steps; soldering needed? |
| C3 | **Time-to-first-flight / teacher burden** | 8 | Unbox → flying in < 30 min; teacher needs no special skills | Needs firmware flashing, soldering, tuning | Timed trial with a new teacher |
| C4 | **Indoor position hold** | 10 | Hands-off hover < 0.3 m drift for 30 s | Pilot must fly every second (acro/angle only) | Drift test on the gym floor |
| C5 | **Programming ladder** | 12 | Blocks → Python/JS → onboard code/ROS, all on the same drone | One level only, or none | Map lessons to grades |
| C6 | **Openness** | 8 | Open firmware and hardware, documented protocol, replaceable parts | Closed firmware, proprietary radio, single vendor | Licenses, docs, SDK |
| C7 | **Durability and repair** | 10 | Survives 1 m drops; spares cheap and student-swappable | Fragile PCB arms; repair needs soldering or the vendor | Drop test; spare-part cost |
| C8 | **Cost per kit** (drone + radio, before shared gear) | 10 | ≤ $100 | > $600 | BOM / list price. 4 = ≤ $250, 3 = ≤ $400, 2 = ≤ $600 |
| C9 | **Vendor longevity / supply** | 7 | Long-lived edu-focused vendor, or multi-source parts | Discontinued or single small seller | Product age, stock, discontinuation history |
| C10 | **Classroom logistics** | 5 | Many drones fly at once without cross-talk; easy charging; classroom packs | Wi-Fi congestion; one charger per pack | 8-drone class trial |
| C11 | **Sensors and expandability** | 5 | Flow, range, camera/ports for add-ons | No sensors exposed to students | Spec sheet |

---

## 4. Candidates

| Platform | Type | Price (as listed) | Key facts |
|---|---|---|---|
| **Robolink CoDrone EDU** | RTF micro (1S) | **$249** (rose from $215 in May 2025); 12-pack $3,599 | 54.8 g, 7–8 min; optical flow, front + bottom ToF (1.5 m), 2 color sensors; Blockly + Python; controller + drone kit; anchors the REC Foundation Aerial Drone Competition |
| **Bitcraze Crazyflie 2.1+ STEM bundle** | Open-source nano (1S, brushed) | **$320** (Flow deck v2 + Crazyradio 2.0) | About 30 g; fully open firmware/hardware; Python cflib, C onboard apps, ROS 2/swarm; deck ecosystem; snap-in motors only |
| **Crazyflie 2.1 Brushless** | Open-source micro (brushless) | STEM bundle price not confirmed (AI bundle $780) | Same software as 2.1+; tougher brushless drive; mostly assembled |
| **Duckiedrone DD24** | DIY Raspberry Pi quad | **$449** official store (resellers $549–749) | Pi 4/5 onboard; Python/ROS autonomy; **soldering required**; college/HS level |
| **LiteWing / ESP-Drone** | ESP32 PCB-frame micro | **≈ $26 bare – $70 RTF** | Crazyflie-protocol compatible (cflib); Wi-Fi link; very cheap; small sellers, spotty stock |
| **Drone Soccer learn kit** (US Drone Soccer) | Caged FPV-style build kit | **$589** per kit (serves 1–3 students) | Students build; crash-proof cage; team sport; **no position hold or autonomy** |
| **Ryze Tello EDU** (baseline) | RTF micro | n/a | **Discontinued** (production 2018–2024; DJI left education). Superb vision-based hold and a huge curriculum base. Its loss is the cautionary tale for C9. |
| **BYM Kestrel K1 v1** | Kid-built 3" ducted quad, ArduPilot | **≈ $485–715/kit** (spec §5) | Ducts + guards, 3S, flow + ToF, Web Serial/MAVLink, Lua onboard; **projected, unbuilt** |

Out of scope: Pixhawk/X500-class dev kits (> 250 g, outdoor, university level).

---

## 5. Scores

### 5.1 Raw scores (1–5)

| Criterion (weight) | CoDrone EDU | CF 2.1+ | CF Brushless | Duckiedrone | LiteWing | Drone Soccer | Tello EDU | **Kestrel K1** |
|---|---|---|---|---|---|---|---|---|
| C1 Safety (15) | 5 | 5 | 4 | 2 | 4 | 4 | 5 | 4 |
| C2 Build value (10) | 1 | 2 | 2 | 3¹ | 2 | 5 | 1 | **5** |
| C3 Time-to-flight (8) | 5 | 4 | 4 | 1 | 3 | 3 | 5 | **2** |
| C4 Position hold (10) | 4 | 4 | 4 | 3 | 2 | 1 | 5 | 4² |
| C5 Prog. ladder (12) | 4 | 5 | 5 | 5 | 3 | 1 | 3 | 4² |
| C6 Openness (8) | 2 | 5 | 5 | 4 | 5 | 3 | 1 | 5 |
| C7 Durability (10) | 4 | 2 | 3 | 3 | 2 | 5 | 3 | 4² |
| C8 Cost (10) | 4 | 3 | 2³ | 2 | 5 | 2 | 5⁴ | **2** |
| C9 Longevity (7) | 4 | 4 | 4 | 3 | 2 | 3 | 1 | 3 |
| C10 Logistics (5) | 5 | 3 | 3 | 2 | 2 | 3 | 3 | 3 |
| C11 Sensors (5) | 4 | 5 | 5 | 5 | 3 | 1 | 3 | 4 |
| **Weighted (BYM)** | **3.82** | **3.85** | **3.70** | 2.96 | 3.09 | 2.91 | 3.36 | **3.70** |

¹ High build depth, but soldering puts it out of reach of middle schoolers. ² Projected from the design; not demonstrated. ³ Price not confirmed; assumed > $400 with the radio. ⁴ Historical price; it can no longer be bought new from the maker.

### 5.2 Sensitivity: ranking under different priorities

| Profile (what changes) | 1st | 2nd | 3rd | Kestrel K1 |
|---|---|---|---|---|
| **BYM baseline** (weights above) | CF 2.1+ 3.85 | CoDrone 3.82 | CF Brushless / Kestrel 3.70 | **3rd–4th (tie)** |
| **MS build focus** (build 20, safety 18, cost 14) | **Kestrel 3.68** | CoDrone 3.63 | CF 2.1+ 3.53 | **1st** |
| **HS autonomy** (prog. 20, pos-hold 14, open 12) | CF 2.1+ 4.14 | CF Brushless 4.04 | CoDrone 3.84 | 4th (3.78) |
| **Budget first** (cost 24) | CoDrone 4.03 | Tello 3.76 | CF 2.1+ 3.68 | 6th (3.29) |

**Robust conclusions:**
- Duckiedrone, Drone Soccer and LiteWing never reach the top three for BYM's mission. They are too hard, can't be programmed for autonomy, or are too immature.
- CoDrone EDU and Crazyflie are always in the top three. They are the right **benchmarks**.
- Kestrel's ranking depends entirely on how much BYM values students *building* the drone.

---

## 6. What it would take for Kestrel to lead

The study points to Kestrel's two cheapest upgrades:

| Change | Criterion move | Baseline | MS build | HS autonomy | Budget |
|---|---|---|---|---|---|
| Kestrel K1 v1 (today) | | 3.70 | 3.68 | 3.78 | 3.29 |
| **+ cost ≤ $400/kit** (value FC tier, shared chargers, 2 packs) | C8 2 → 3 | +0.10 | +0.14 | +0.08 | +0.24 |
| **+ one-click BYM Configurator** (web app flashes params, checks motor order/sensors, guides binding) | C3 2 → 3 | +0.08 | +0.10 | +0.06 | +0.10 |
| **Kestrel Rev B** | | **3.88 (1st)** | **3.92 (1st)** | 3.92 (3rd, 0.22 behind CF 2.1+) | 3.63 (4th) |

The bigger structural risks are **C4/C5/C7 being unproven**. Scores marked ² must be confirmed by the instructor-kit bench and flight tests (spec §11) before this study's Kestrel numbers mean anything.

---

## 7. Design principles for BYM (the "what makes it good" answer)

1. **Safety is the license to operate.** Decide it with mass and enclosure, not rules alone. Under 60 g, or fully ducted/caged, plus a physical kill switch and failsafes that land the drone.
2. **Position hold before programming.** Students can't write `forward(0.5)` for a drone they have to fight. A drone that hovers by itself (flow + range) is the prerequisite for every coding lesson. It is also why the Tello was so loved.
3. **One drone, many rungs.** The same hardware should take a student from Blockly at 11 to Python and onboard code at 17. Platforms with one rung (Drone Soccer: flying only; Tello: SDK only) cap growth.
4. **Build what's safe to build; buy what must be reliable.** Kids assemble the airframe, motors and plugs. Flight-critical electronics stay proven COTS. This is Kestrel's core philosophy, and the study supports it as the way to get build value without sacrificing C4.
5. **Design for the 50th crash.** Count spare cost per class, not just kit cost. Printed parts cost cents to replace; that is a real advantage over sealed RTF drones.
6. **The teacher is the user too.** The literature's top barriers are teacher readiness and cost/sustainability. Anything needing firmware skills must be wrapped in a guided tool.
7. **Avoid single-vendor dead ends.** Prefer open firmware, standard protocols (MAVLink/CRTP) and multi-source parts. Your mRo AIO experience and the Tello's exit are both versions of this lesson.

---

## 8. Recommendations and next steps

1. **Benchmark set (about $570):** one CoDrone EDU ($249) and one Crazyflie 2.1+ STEM bundle ($320). Run the C3/C4/C7 tests on them **and** on the Kestrel instructor kit with the same protocol (timed unbox-to-hover, 30 s drift test, 10× 1 m drop test).
2. **Set Kestrel Rev B requirements from §6:**
   - ≤ $400/kit,
   - a guided BYM Configurator in the web app,
   - ≤ 200 g,
   - a flow-sensor clip,
   - a 180 mm-bed variant.
3. **Program structure option (your call):** a **hybrid** program. Use CoDrone EDU or Crazyflie for programming-first units, where the drone is a tool. Use Kestrel for build-and-fly units and the high-school ArduPilot track, where the drone is the project. This also hedges Kestrel schedule risk.
4. **Re-score after testing.** Replace the projected (²) scores with measured ones, then decide whether Kestrel goes to a 4-kit pilot class.

### Open questions for you
- **How much do you value students building the drone?** Section 5.2 shows this weight alone decides whether Kestrel is the right primary platform.
- Does BYM need **REC Foundation Aerial Drone Competition** compatibility? That competition uses the CoDrone EDU, which would strongly favor it for competition teams.
- Federal or grant funding rules (e.g. Section 889/NDAA drone restrictions) at your partner schools? All candidates except the Tello avoid DJI.

---

## Sources
- Robolink CoDrone EDU price update (May 2025): https://www.robolink.com/blogs/roblog-link/codrone-edu-price-update-keeping-stem-and-cte-accessible-2
- CoDrone EDU technical specifications v1.1: https://docs.robolink.com/assets/files/cde_technical_specifications_v_1_1-f30e6119adce4bd8ca75457bc7515ce9.pdf; sensor guide: https://docs.robolink.com/docs/CoDroneEDU/Resources/Sensor-Guide/
- CoDrone EDU classroom packs: https://www.robotshop.com/products/robolink-codrone-edu-classroom-12-pack
- Bitcraze STEM drone bundle (Crazyflie 2.1+): https://store.bitcraze.io/products/stem-drone-bundle; STEM ranging bundle: https://store.bitcraze.io/products/stem-ranging-bundle
- Crazyflie 2.1 Brushless AI bundle: https://store.bitcraze.io/collections/bundles-crazyflie-2-1-brushless/products/the-ai-bundle-crazyflie-2-1-brushless
- Duckiedrone DD24: https://get.duckietown.com/products/autonomous-raspberrypi-quadcopter-duckiedrone-dd24
- LiteWing (ESP32, Crazyflie-compatible): https://circuitdigest.com/litewing; https://www.cnx-software.com/2024/09/21/low-cost-diy-esp32-drone-12-dollars/
- US Drone Soccer kits and StemFinity DIY soccer drone kit: https://stemfinity.com/products/diy-soccer-drone-kit
- Ryze Tello status: https://en.wikipedia.org/wiki/Ryze_Tello; https://www.digitalcameraworld.com/news/dji-tello-drone-is-set-to-disappear-as-drone-giant-ditches-education
- Slater (2024), implementation strategies for drones in STEM/CTE, *Education Sciences*: https://doaj.org/article/5431ed534baf4bda866f646e503e0ec6
- Teacher readiness case study: https://www.informingscience.org/Publications/4288
- BYM Kestrel K1 design spec: [BYM_Kestrel_K1_Design_Spec.md](BYM_Kestrel_K1_Design_Spec.md)
