## AI at EIC

The Electron-Ion Collider (EIC){cite}`EIC-YellowReport` is a cutting-edge accelerator facility that will study the nature of the "glue" that binds the building blocks of the visible matter in the universe. The proposed experiment will be realized at Brookhaven National Laboratory in approximately 10 years from now, with detector design and R&D currently ongoing. Notably, EIC is one of the first large-scale facilities to leverage Artificial Intelligence (AI) already starting from the design and R&D phases. The EIC Comprehensive Chromodynamics Experiment (ECCE) is a consortium that proposed a detector design based on a 1.5T solenoid.

AI can provide new insights and discoveries from both experimental and computational data produced at user facilities.

More information on AI activities at EIC can be found at [ai4eic](https://eic.ai)

---

## AI workflow for detector design

Performance of the tracker is key to achieve the goals of the EIC physics program. The current tracker system in the EIC Detector 1 concept is assisted by AI. And the AI assisted optimization is anticipated to continue until the final R&D stage. Optimizing such a large-scale detector is a very complex problem. Each sub-detector systems by itself is a complex design problem. In addition detector simulations could be very much resource intensive (like in [`GEANT4`](https://geant4.web.cern.ch)). This becomes the bottle neck for deep learning (DL) based approaches that learn the mapping between design space and the functional space. Fast Simulations with DL can indeed reduce the bottle neck, several design points need to be produced with `GEANT4` before injection in any DL architecture.

Therefore, in the recent years, a workflow containing sequential AI-based strategy is gaining popularity. The workflow is outline below in {numref}`eic-design-workflow`.

```{figure} ./images/design_workflow.png
---
name: eic-design-workflow
---

**Workflow of detector design assisted by AI** Also, refer various AI based strategies discussed in the [lecture 1 CHANGE IT TO CORRECT ONE](https://docs.google.com/presentation/d/1gCQ0jeSJVSCiGt511XHdH-vJXh9hHKvzWEW2W4Rx19M/present?usp=sharing)
```

In the above outlined workflow, physics events are injected

---

## Interplay between expertise

To effectively design the detector, there has to be a effective and a constant communication between various expert groups. The figure {numref}`eic-interplay-groups` shows the significance of interplay between different working groups. This model was followed to design the tracking system {cite}`AI-assisted-paper` proposed by [ECCE](https://www.ecce-eic.org) and currently being followed to further optimize the tracker (and possibly the PID systems)


```{figure} ./images/interplay_groups.png
---
name: eic-interplay-groups
---

**Flowchart of continual optimization** The figure shows the information flow between different working groups and summarizes the "Continual" optimization of a detector.
```
(sec-opt-continous)=
### Optimization as a continuous process

Detector optimization is a continuous and an iterative process. For the optimization of the tracking system, the process can be briefly summarized as:

+ At a given instant in time we have a `Phase` of optimization. During a current `Phase` of optimization we have `N` alternative candidate configurations that are studied (`Configurations`)

+ For each of the `N` configurations that are being explored, we start with a `N` baseline designs. Potential optimization parameters are identified in each of the configurations like the geometric parameters, number of subdetector systems, spatial resolutions of the detector system, etc.

+ Then each of `N` configurations are now optmized in separate pipelines, which results in a Pareto front of solutions. This new information helps steer the design: some configurations are rejected, while other ones (also dubbed 'new references') are identified to potentially improve the design. This is where we have the intervention of detector and physics working groups. They provide feedback on potential designs that could be realized and may identify designs that can be further optimized. New optimization pipelines are defined inspired by the new results and the process is iterated. Each time the goal of optimization is to improve against a given reference design.

Therefore, We have different `Phases` of optimization corresponding to timeline it was explored. Each of the `Phases` has `N` configurations explored in them, And each of the `N` configurations can have `M` iterations of optimization pipelines.

So far 2 Phases of optimizations are done for the tracking system. Phase-I explored various choice of detector technologies that can be used to build the tracker, The simulations contained little information about the tracking support system, and Phase-II involved more realistic simulations and support for tracking and incorporated general engineering constraints. Ee are currently in the $3^rd$ phase of optimization. This mainly will involve additional/stricter engineering constraints and include backgrounds in the optimization.

---



```{bibliography}
```
