# DeskCNC-Plotter
Theoretical design and documentation in Fusion360 on a desktop CNC milling machine for different materials

DeskCNC is a compact desktop CNC machine designed as a learning and practice alternative for manufacturing simple and custom PCBs.
The project explores the integration of CAD design, weight distribution, mechanical transmission and basic programming (not yet tho...) to create a fast, space-efficient milling solution

**Core Purpose**
Rapid fabrication of PCBs and general purpose plotting while letting a free way to external modifications

# Design Evolution

1.**Iteration #1: - Rack and Pinion Prototype**

The initial concept focused on converting rotational motion to linear motion using a rack and pinion system

Technical Challenges: Encountered significant backlash, a few weight distribution issues and excessive footprint expansion during the operation

Key Learning: In-depth study of gear geomtry, tooth spacing formulas and Cartesian coordinate movement

2.**Iteration #2: - GT2 belt & Pulley System**

To address the footprint issues, the design transitioned to a "closed" system using GT2 timing belts

Optimization: Replaced the expanding racks with GT2 belts and pulleys while adding bearings to the Y-Axis

Stability: Bearings provided extra support for the weight of the Z-Axis servomotor and the Y-Axis stepper

Simulation: Developed Motion Links in F360 to simulate logical motion withouth needing detailed belt teeth models.

3.**Iteration #3: - Rod-Stabilized Design (Current)**

The final iteration focuses on weight distribution and structural rigidity.

"Supported Beam" Solution: Transitioned from a cantilever-style structure to a supported beam system. By adding sliding rods, the weight is distributed across the entire work area rather tahn resting solely on the belts

Efficiency: This configurationb mantains the original compact dimensions while drastically increasing stability and mobility

# Mechanical Sim & Math

To ensure precision in the digital twin, the Motion Link relationship was calculated based on GT2 belt specifications

**Formula:**
  $$M = D \cdot Dc$$

D-(Pulley Theet) = 12
Dc-(Belt Pitch) = 2mm
M-(Total movement per 360° rev) = 24mm

**Resolution Scaling**
-24mm = 360°
-12mm = 180°
-1mm = 15°

# Small Specifications

In the third design, the working are is 15cm x 19cm, all three designs are meant to work with Arduino/Esp32 + CNC ShieldV3 and Stepper Motors (28BYJ-48)
