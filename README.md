# KONTUMA — Sheet Metal Bending Simulation
<img src="./photo/3D симуляция гибки.png" alt="3D bending simulation" width="700">

A Windows application for preparing and simulating sheet metal bending on CNC press brakes.

🌐 **Landing page:** https://koksasa.github.io/Kontuma/

---

## What is KONTUMA

KONTUMA closes the full workflow of a bending technologist — from a DXF/STEP part file to a ready bending map and a step-by-step operator instruction on a shop-floor tablet.

Load a drawing, and the software automatically:

- finds bend lines,
- builds a 3D model of the part,
- selects tooling from the library,
- places punches and dies along the machine ram,
- calculates bending force and backgauge distances,
- checks collisions (punch, die, machine, floor),
- generates a PDF passport and a `.opjob` job file.

An operator then opens the `.opjob` file on a tablet in the shop and sees a clear step-by-step instruction with a photo of every bend.

---

## Problem → Solution

Every mistake at the press costs metal, time and machine repairs. KONTUMA moves verification into the digital world — before the operator presses the pedal.

**Without KONTUMA:**

- Operator bends the wrong way — the part is scrapped
- Technologist calculates backgauge by hand in Excel — errors
- Punch hits the die — machine repair
- Hole too close to the bend — metal tears
- No single bending passport — everyone does it their own way

**With KONTUMA:**

- 3D simulation BEFORE bending at the machine
- Backgauge and force calculated automatically
- Real-time collision checking
- Warning: "hole too close to bend"
- PDF passport + operator tablet with a photo of every bend

---

## Features

### 1. DXF and STEP import
Recognizes bend lines by layers and line types, stitches the contour, supports automatic detection of virtual bends from micro-cuts.

### 2. Tooling library
Punches and dies from DXF. Mirroring along X/Y/Z, binding to the machine.

### 3. Automatic tooling placement
The software picks the required punch and die length for each bend and lays them along the ram without overlaps. Respects granularity — the shortest bend gets the shortest punch.

### 4. 3D bending simulation
Smooth animation: the workpiece rotates, the punch descends, the part bends. You see how the part will sit on the die BEFORE the operator starts.

### 5. Collision check
Red highlight: punch, die, ram, bed, back gauges, floor. Warnings in the bend table: "workpiece hits the punch", "hole too close to bend". Includes a reset button for false positives.

### 6. Force and backgauge calculation
Bending force in tonnes by material, thickness, V-opening of the die and bend length. Distance from machine axis to the backgauge — with the K-factor of the neutral layer.

### 7. Bending cycle time
Calculation of machine and operator time: loading, alignment, backgauge adjustment, working stroke, unloading. Export to Excel.

### 8. Operator passport
PDF with punch and die profiles, flat pattern, overall dimensions, mass and a photo of every bend. The `.opjob` file opens on a tablet in the shop — the operator sees a step-by-step instruction with progress checkmarks.

---

## Two interfaces — one file, two roles

**Technologist** — Windows application with a large 3D view, tooling panel, bend table, force and collision calculation.

**Operator** — tablet in the shop. Bend tiles with photos, counter `✅ 3/8`, blue "Done" button. No internet required.

One job file `.opjob` — and both the technologist and the operator work with the same version of the part. No "I was using an old drawing".

---

## Export and integration

- **PDF bending passport** — A4, ready to print
- **Excel bend table** — for MES / ERP
- **Job file `.opjob`** — for the operator tablet
- **3D view screenshot** — PNG for proposals and documentation

---

## Technical capabilities

- **DXF support** — LINE, LWPOLYLINE, ARC, CIRCLE
- **STEP parsing** — via OpenCascade
- **K-factor of the neutral layer** — 0..1, preset 0.3–0.5
- **Springback calibration** — table of Y values by material / thickness / angle / V
- **Automatic bend sorting** — by ascending backgauge distance
- **Face flip, backgauge change, workpiece rotation**
- **Custom dimensions** — ram, bed, back gauges with cutouts
- **Workpiece section by plane** — visual cut
- **HUD of overall dimensions and part mass**
- **Auto-run of all bends** — in order, for the technologist to review

---

## Why KONTUMA

- Works fully offline — no cloud, no subscriptions
- Native Windows application — installs in 5 minutes
- Unlimited operator tablets per license
- Operator instructions open locally on a tablet in the shop
- Dozens of times cheaper than Radan, Lantek Bend, TruTops Bend

---

## Tech stack

`HTML` · `CSS` · `Vanilla JavaScript` · `No frameworks` · `No CDN` · `Works offline`

---

## License

MIT — see [LICENSE](LICENSE).
