# Introduction to Robotics Lab — Interactive Site

A live, in-browser visualization companion to **IE University's Introduction to Robotics Lab** (IRL-N3CSAI). Every core concept from the syllabus has a hands-on interactive demo:

| Module | Concept | What you can do |
| --- | --- | --- |
| 1 | History of Robotics | Click any era in the timeline to expand it |
| 1 | Robotics & AI | Click each node of the Sense→Think→Act loop |
| 1 | Kinematics | Drag end-effector for IK, or move sliders for FK on a 2-link arm |
| 2 | Sensors | Live ultrasonic, IR line follower, and rotary encoder simulators |
| 2 | Actuators | DC motor + PWM, servo, gearbox trade-off |
| 2 | Control | Tune PID gains live on a 1-DOF cart |
| 3 | Pepper Robot | Trigger Choregraphe-style behaviors on an interactive Pepper avatar |
| 3 | NLP | Type commands, watch a tokenizer/intent classifier work |
| 4 | Pi Car Build | Interactive GPIO pinout — click any pin |
| 4 | Autonomous Navigation | Drive a simulated Pi car or let the reactive controller drive |

Everything runs **client-side in pure HTML/CSS/JS**. No build step, no dependencies, no backend.

## Deploy to GitHub Pages

### Option A — `gh` CLI (fastest)

```powershell
cd C:\Users\ASUS\Desktop\ROBOTICS
git init
git add .
git commit -m "Initial interactive robotics site"
gh repo create robotics-lab-interactive --public --source=. --push
gh api -X POST "repos/{owner}/{repo}/pages" -f "source[branch]=main" -f "source[path]=/"
```

Your site will be live at `https://<your-username>.github.io/robotics-lab-interactive/` in 1-2 minutes.

### Option B — manual

1. Create a new public repo on github.com (e.g. `robotics-lab-interactive`).
2. In this folder:
   ```powershell
   git init
   git add .
   git commit -m "Initial interactive robotics site"
   git branch -M main
   git remote add origin https://github.com/<your-username>/robotics-lab-interactive.git
   git push -u origin main
   ```
3. On GitHub: **Settings → Pages → Source: Deploy from branch → main / (root)**.

## Local preview

Just open `index.html` in any browser. For best results (clean URLs, no file:// quirks), serve via Python:

```powershell
python -m http.server 8000
# then visit http://localhost:8000
```

## Repository layout

```
ROBOTICS/
├── index.html              ← landing page
├── css/main.css            ← all styling
├── pages/
│   ├── history.html        ← Module 1: History timeline
│   ├── ai.html             ← Module 1: Sense→Think→Act
│   ├── kinematics.html     ← Module 1: 2-link arm FK/IK
│   ├── sensors.html        ← Module 2: ultrasonic, IR, encoder
│   ├── actuators.html      ← Module 2: DC, servo, gearbox
│   ├── control.html        ← Module 2: PID simulator
│   ├── pepper.html         ← Module 3: Pepper avatar
│   ├── nlp.html            ← Module 3: intent classifier
│   ├── raspi-car.html      ← Module 4: GPIO pinout
│   └── autonomous.html     ← Module 4: drivable car maze
├── .nojekyll               ← tells GitHub Pages not to run Jekyll
└── SyllabusPDF_*.pdf       ← original syllabus
```

## Credits

Based on the syllabus for *Introduction to Robotics Lab* taught by **Prof. Suzan T S Awinat** at IE University, 2025–2026 academic year. Not officially affiliated with IE University.

Built with vanilla HTML / CSS / Canvas / SVG — no frameworks.
