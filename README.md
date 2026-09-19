<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0B7A75,100:2E9EF7&height=180&section=header&text=Shivendu%20Kumar&fontSize=54&fontColor=ffffff&animation=fadeIn&fontAlignY=36&desc=Robotics%20·%20Computer%20Vision%20·%20Simulation&descAlignY=58&descSize=18" width="100%"/>
</div>

<div align="center">

[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=26&pause=1100&color=0B7A75&center=true&vCenter=true&width=620&lines=Autonomous+systems+that+know+where+they+are;Computer+vision+that+survives+bad+input;CFD+and+aeroacoustics+at+NIT+Patna;Chanakya+Undergraduate+Fellow+%7C+TEXMiN)](https://git.io/typing-svg)

<a href="mailto:kumarshivendu47@gmail.com"><img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white"/></a>
<a href="https://www.linkedin.com/in/shivendu-kumar-5971112b9"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white"/></a>
<a href="https://shivendukmr.github.io"><img src="https://img.shields.io/badge/Portfolio-0B7A75?style=for-the-badge&logo=firefox&logoColor=white"/></a>

<img src="https://komarev.com/ghpvc/?username=ShivenduKmr&color=0B7A75&style=flat-square&label=Profile+views"/>

</div>

---

## About

I build machines that have to work out where they are and what they are looking at — a racing car
with no driver, a drone mapping a mine where GPS cannot reach, a camera sorting waste on a moving
belt. Most of my useful work has been figuring out **why something failed when the obvious
explanation was wrong.**

```python
class ShivenduKumar:
    def __init__(self):
        self.education   = "B.Tech Mechanical Engineering @ NIT Patna"
        self.cgpa        = 8.06
        self.graduating  = 2027
        self.fellowship  = "Chanakya UG Fellow, TEXMiN @ IIT (ISM) Dhanbad"
        self.papers      = 2          # one as first author
        self.available   = "6-month internship from mid-December 2026"

    def what_i_actually_do(self):
        return {
            "perception":  ["sensor fusion", "SLAM", "vision transformers"],
            "control":     ["PID", "Pure Pursuit", "unscented Kalman filter"],
            "simulation":  ["ANSYS CFX", "LES-WALE", "FW-H acoustics"],
            "when_stuck":  "stop assuming, go look at the raw data",
        }
```

---

## Experience

| Where | Role | When |
|---|---|---|
| **Shoonya Recycling**, New Delhi | Product Analytics & Computer Vision Intern | May – Jul 2026 |
| **Vazirani Automotive**, Mumbai | System Design Intern | May – Jul 2026 |
| **IIT Jodhpur**, School of AI & Data Science | Robotics Research Intern | May – Jul 2025 |

<details>
<summary><b>What I actually did →</b></summary>

<br>

**Shoonya Recycling** — An automated sorting line was missing throughput and nobody could say why.
My first assumption was the model needed more training data. It did not. Comparing misclassifications
against what physically happened on the belt showed the failures clustered on **motion blur and
underexposure** — an input problem, not a model one. Fixed with CLAHE contrast enhancement and a
move from a CNN to a vision transformer, whose global attention holds up where local texture is
unreliable.

**Vazirani Automotive** — Designed an axial fan compressor doing two jobs at once: generating
downforce and feeding forced-air cooling to the battery pack. Ran the baseline CFD in ANSYS — a
blade passage meshed in TurboGrid to a 3 µm first cell, then the 11-blade, 12,000 rpm stage solved
in CFX with SST *k*–ω at 0.07 kg/s.

**IIT Jodhpur** — Fused camera, ground-penetrating radar and IMU streams from UAV trials into one
perception pipeline across three different sampling rates and failure modes. Built the evaluation
harnesses that made detection performance legible across terrain.

</details>

---

## Featured work

### Search-and-rescue UAV — dual-modality detection
<img align="right" width="330" src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExbXJ2aWJqZzV5cGJ0MnN5Y3RuYjhyZTZkdWh5ZnRoeWJ1aXVoeWRhNSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/LaVp0AyqR5bGsC5Cbm/giphy.gif"/>

Two ways of finding people: **YOLOv5** on the surface, simulated **GPR** below it.
**84.7% detection confidence across 50+ runs.** The part worth talking about is not the number —
it is knowing which conditions made each sensor lie.

A* global planner with dynamic obstacle avoidance and cascaded PID control, built in Webots.

`Python` `PyTorch` `Webots` `SciPy` `NumPy`

📄 **Published** — *Modeling and Simulation of UAV-Based Search and Rescue*, ICAMAS 2026

[**→ Repository**](https://github.com/ShivenduKmr/rescue_drone_2)

<br clear="right"/>

---

### F1/10th autonomous racing stack

Nobody assigned this one. A full autonomous racing stack on Linux:

- **2D LiDAR SLAM** with particle-filter (AMCL) localisation
- Closed-loop **Pure Pursuit** path tracking
- Reactive **gap-finding** controller that picks a line through obstacles at speed

`ROS` `C++` `Python` `Gazebo` `Linux`

[**→ Repository**](https://github.com/ShivenduKmr/F1-tenth-autonomous-racing)

---

### Mapping a mine with no GPS and no light

Underground tunnels defeat visual localisation: no ambient light, and brick walls that repeat every
few metres so every frame looks like the last.

An **unscented Kalman filter** fusing 100 Hz IMU with sparse visual features and LiDAR cut
positional drift **82.4%, down to 0.07 m** over a 60 m gallery. Artificial potential field for
obstacle avoidance, and a 3D digital twin built from the LiDAR returns.

`ROS2` `Gazebo Fortress` `UKF` `V-SLAM`

📄 **First author** — *AI-Enabled Autonomous Mapping in Underground Environments*
· Funded by the TEXMiN Chanakya Undergraduate Fellowship

---

### Why half a good idea made things worse

Owl-inspired serrations on a UAV propeller, three geometries, transient large-eddy simulation with
the Ffowcs Williams–Hawkings acoustic analogy.

- Full-span serration cut noise by **3.87 dB** (OASPL)
- Serrating only **half** the blade made it **1.87 dB worse**
- The cause was not the serration but the **junction** between treated and untreated sections

The transition was wrong, not either half. That result is the reason the study was worth doing.

`ANSYS Fluent` `LES-WALE` `FW-H` `Fusion 360`

[**→ Repository**](https://github.com/ShivenduKmr/Fluent-analysis-of-serrated-airfoil)

---

### Industrial autonomous mobile robot

A 500 × 500 × 500 mm chassis carrying **20 kg at 1 m/s**, drivetrain sized from first principles to
a 2.0 safety factor (127.3 RPM, 27.5 N). 6 mm aluminium 6061 base plate, an ABS mezzanine isolating
the compute from motor vibration, and a **TS35 DIN rail** so standard components mount without
custom brackets.

`Fusion 360` `Kinematics` `Structural analysis`

---

### Health Atlas — EY Techathon 6.0

<img align="right" width="330" src="https://media.giphy.com/media/L8K62iTDkzGX6/giphy.gif"/>

**Semifinalist from 115,000+ registrations.** A healthcare analytics product taken from research to
working software in a competition sprint — market and competitor research, then requirements and
wireframes, then a multi-agent pipeline with an NLP layer turning unstructured reports into ranked
KPI dashboards a non-technical reader can act on.

`Multi-agent AI` `NLP` `Streamlit` `Figma` `Python`

[**→ Repository**](https://github.com/Rupali2507/Health_Atlas)

<br clear="right"/>

---

## Stack

<div align="center">

**Languages**

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=for-the-badge&logo=c%2B%2B&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=postgresql&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)

**Robotics & perception**

![ROS](https://img.shields.io/badge/ROS_2-22314E?style=for-the-badge&logo=ros&logoColor=white)
![Gazebo](https://img.shields.io/badge/Gazebo-F58025?style=for-the-badge)
![Webots](https://img.shields.io/badge/Webots-6DB33F?style=for-the-badge)
![SLAM](https://img.shields.io/badge/SLAM-4ECDC4?style=for-the-badge)
![Sensor Fusion](https://img.shields.io/badge/Sensor_Fusion-00BFA5?style=for-the-badge)

**Vision & ML**

![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white)
![YOLO](https://img.shields.io/badge/YOLOv5-00FFFF?style=for-the-badge&logoColor=black)
![ViT](https://img.shields.io/badge/Vision_Transformers-5849BE?style=for-the-badge)

**Simulation & CAD**

![ANSYS](https://img.shields.io/badge/ANSYS-FFB71B?style=for-the-badge&logo=ansys&logoColor=black)
![CFX](https://img.shields.io/badge/CFX_·_TurboGrid-FF6B00?style=for-the-badge)
![SolidWorks](https://img.shields.io/badge/SolidWorks-FF0000?style=for-the-badge)
![Fusion360](https://img.shields.io/badge/Fusion_360-FF6B00?style=for-the-badge)

</div>

---

## Stats

<div align="center">

<img height="165em" src="https://github-readme-stats.vercel.app/api?username=ShivenduKmr&show_icons=true&theme=tokyonight&include_all_commits=true&count_private=true&hide_border=true"/>
<img height="165em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=ShivenduKmr&layout=compact&langs_count=8&theme=tokyonight&hide_border=true"/>

<img src="https://streak-stats.demolab.com?user=ShivenduKmr&theme=tokyonight&hide_border=true" alt="Streak"/>

<img src="https://github-profile-trophy.vercel.app/?username=ShivenduKmr&theme=tokyonight&no-frame=true&no-bg=true&margin-w=8&column=7" width="100%"/>

<img src="https://github-readme-activity-graph.vercel.app/graph?username=ShivenduKmr&theme=tokyo-night&hide_border=true&area=true" width="100%"/>

</div>

---

## Honours

| | |
|---|---|
| 🎓 | **Chanakya Undergraduate Fellow** — TEXMiN Foundation, IIT (ISM) Dhanbad. One of a small number of undergraduates nationally funded to define and run an independent research project. |
| 🥇 | **1st place & Best Speech** — UNESCO-WWDR Model UN, for a data-backed technical strategy on antimicrobial resistance argued before an international panel. |
| 🛰️ | **Team Sub-Lead** — ISRO URSC Challenge 2026. Led technical contributions and hardware integration to the national elimination round. |
| 💡 | **Semifinalist** — EY Techathon 6.0, from 115,000+ registrations. |
| 🌊 | **Finalist** — EU-India Ideathon 2025, marine plastic pollution, among 150+ international participants. |
| 📊 | **Ranked 25 nationally** — Naukri Campus EROH, from 110,000+ applicants. Top 5 at Material Spark 2025, IIT Patna. |

<details>
<summary><b>Leadership & positions →</b></summary>

<br>

| Role | Organisation | When |
|---|---|---|
| Office Bearer | Hackslash Developers Club, NIT Patna | Aug 2025 – present |
| Event & PR Lead | ISIE NITP SRA | Oct 2024 – Dec 2025 |
| Content Team | Hackslash Developers Club | Aug 2024 – May 2025 |
| Sponsorship Lead | ByteVerse Annual Hackathon, NIT Patna | 2025 |
| Organiser | Smart India Hackathon presentation round, NIT Patna | 2025 |

**Certifications** — Design for 3D Printing (Udemy) · Computer Integrated Manufacturing (NPTEL)

</details>

---

## What I am working on

```mermaid
mindmap
  root((Shivendu))
    Perception
      Sensor fusion
      SLAM and localisation
      Vision under degraded input
    Control
      Unscented Kalman filtering
      Closed-loop tracking
      Path planning
    Simulation
      LES and aeroacoustics
      Turbomachinery CFD
      Digital twins
    Open questions
      Why vision fails when input degrades
      Localising without GPS or light
```

---

<div align="center">

### Open to a six-month internship from mid-December 2026

Robotics · computer vision · simulation · product

**kumarshivendu47@gmail.com**

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:2E9EF7,100:0B7A75&height=110&section=footer"/>

</div>
