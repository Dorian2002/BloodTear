# BloodTears

![Logo](https://i.imgur.com/GlsujWz.png)
**BloodTears - Technical Design, Tech Lead & Systems Architecture**

BloodTears is a systemic hack-and-slash game developed using Unreal Engine 5.4. As Lead Developer, my role was to build a “bridge” between the Game Designer's creative vision and the development team constraints, favoring modular and designer-friendly architectures.

Note: This repository is a fork dedicated to highlighting my personal contributions to the project.  
See the main repository here : [https://github.com/Tractorou24/BloodTear ](https://github.com/Tractorou24/BloodTear)  
Or the Itch.io page here : [https://dorianf.itch.io/blood-tears](https://dorianf.itch.io/blood-tears)  

## Core Contributions
### 1. Gameplay Ability System (GAS) Architecture
I implemented GAS as the technical foundation for all combat interactions.

**Modularity:** Creation of EnsAbilitySystemComponent to natively bind Unreal engine Enhanced Input to Gameplay Abilities.

**Synchronization:** Development of custom AttributeSets (Health, Movement) with automatic updating of native components (e.g., MaxSpeed synchronized with CharacterMovementComponent).

**Scalability:** Intensive use of ScalableFloat to allow the Game Designer to balance progression curves without touching the code.
<img width="3338" height="1088" alt="Diagramme vierge (2)" src="https://github.com/user-attachments/assets/96662538-f00d-405d-ab99-b8ea850a6710" />

### 2. High-Performance AI Systems
The AI was designed to support the envisoned mass combat without compromising the frame rate.

**Custom Vision System:** After a benchmark we replaced the native PawnSensing with a lightweight system based on Line Traces, allowing for a jump from 40 to 60 FPS with 30+ active AIs.
![PM2_Benchmark-ezgif com-optimize](https://github.com/user-attachments/assets/f510cddb-320d-4d60-be91-fd603bbbf3e6)

**Modular Behavior Tree:** Architecture based on reusable decision blocks, separating high-level logic from the execution controller.
![PM2_Math](https://github.com/user-attachments/assets/3b6ceef7-3365-434e-ae49-4f49f54485fa)
![ProtoPM2-Gobelin_6](https://github.com/user-attachments/assets/6d3be44c-4611-4a25-910e-931e927e9716)

### 3. Designer-Centric Tooling & Mediation
As Lead Developer, I acted as the technical pivot for the creative team, implementing tools and processes to facilitate iteration and game balancing. 

**Training Dummy:** Designed a static training dummy that allowed the Game Designer to test and balance weapon metrics (range, damage, etc.) in isolation, without the unpredictable variables of combat against AI. 
![PM2_TrainingDummy-ezgif com-optimize](https://github.com/user-attachments/assets/bdda4421-6304-4dd0-9cbc-5c02b92f2ebb)  

**Technical Mediation & Optimization:** Systematic analysis of the cost/benefit ratio of requested features. For example, I proposed replacing a “pitfall trap” system (complex because it required specific gravity management) with fixed “ground spikes,” preserving the gameplay intent while reducing technical debt. 
![PM2_Trap-ezgif com-optimize](https://github.com/user-attachments/assets/8bed2287-f5af-4e7b-91c0-0e18312b0af5)

**Visual Debugging Tools:** Implementation of probes and visual feedback (hitboxes, detection radius, real-time logs) to make internal systems “readable” for designers, allowing them to understand and adjust behaviors. 
![PM2_BetaSkullKamikaze-ezgif com-optimize](https://github.com/user-attachments/assets/cb35dbfc-746c-4e30-83b0-ecb8214d043c)

**Modular Test Map:** Creation and maintenance of a dedicated test scene, continuously updated with the latest project features to provide a stable and fast validation environment for each new iteration.

## Problem Solving & Iteration
**The Control Pivot (UX/Technical Alignment)**
Initially based on a Diablo-style model, testing revealed player frustration with placement.

Action: I led the technical transition to a ZQSD + Directional Attacks system (Ravenswatch style).

Result: An immediate improvement in user engagement and tactical precision.  
Alpha Movements :
![PM2_MovementsAlpha-ezgif com-optimize](https://github.com/user-attachments/assets/a49ca9b8-3f5b-4546-9f33-1c3fedbc4d0c)
Beta Movements :
![PM2_Movements-ezgif com-optimize](https://github.com/user-attachments/assets/b16e558c-da34-468b-bcad-cd599f554099)

**Asynchronous Bug Squashing**

Case Study: Resolution of a critical AI “Double Jump” bug through detailed analysis of Behavior Tree decision cycles and the addition of locking Decorators to avoid asynchronous race conditions.

## Engineering Standards

**C++ / Blueprints Hybrid:** Heavy logic and mathematical systems in C++ for performance, exposed via clean functions for rapid iteration in Blueprints.

**Code Robustness:** Generalization of the Early Return pattern, use of ensure and assert macros to prevent technical debt.

**Workflow:** Git branching strategy by feature, systematic code reviews, and continuous integration via milestones.

## A bit of fun
Playing baseball with AIs
![PM2_Baseball](https://github.com/user-attachments/assets/055000aa-79bb-47dc-b83f-65e4e9867afa)

## Contributors

**_Game Artists:_**  
[Rémi ANDREZ](https://github.com/AndrezRemi)  
[Benjamin CHAILLET](https://github.com/Benji2725)  
[Quentin DAVID DE VIGNERTE](https://github.com/Shemoon2)  
[Julien DELAGE](https://github.com/TheJulienDELAGE)  
[Mathieu GOMES](https://github.com/math3133)  
[Arthur MUTAUX](https://github.com/Rochtfield)  

**_Game Designer:_**  
[Brian WITKOWSKI](https://github.com/BrianGit06)

**_Developers:_**  
[Dorian FONSECA](https://github.com/Dorian2002)  
[Kevin GRANGER](https://github.com/Kraizix)  
[Fabian INGREMEAU](https://github.com/Tractorou24)
