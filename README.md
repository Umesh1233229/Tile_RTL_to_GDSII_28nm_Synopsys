#  Tile Block – Complete RTL to GDSII Implementation (28nm)

##  Author
Thotla Umesh  

##  Tools Used
- Synopsys Design Compiler (DC)
- Synopsys ICC2
- Tcl Scripting
---
#  Project Overview

This project demonstrates a complete end-to-end RTL-to-GDSII physical design implementation of a macro-dominant Tile block at 28nm technology node.

The entire ASIC flow was executed manually using Synopsys DC,ICC2, including synthesis, floorplanning, placement, clock tree synthesis, routing, timing closure and final signoff verification.

---

#  Block Specifications

| Parameter | Value |
|------------|--------|
| Technology Node | 28nm |
| Clock Period | 1.7 ns |
| Total Cells | 413,935 |
| Sequential Cells | 101,188 |
| Combinational Cells | 312,709 |
| Number of Macros | 18 |
| Core Utilization | 70% (Initial) |
| Final Utilization | 80.7% |

---

# Stage-wise QoR Summary

| Stage | Setup WNS | TNS | Violations |
|--------|------------|------|------------|
| Synthesis | -0.11 ns | -81.21 | 2458 |
| Placement | -0.24 ns | -10.67 | 780 |
| CTS | -0.32 ns | -46.93 | 1416 |
| Post Route | +0.02 ns | 0 | 0 |

✔ Achieved full setup timing closure  
✔ Achieved hold closure (+0.28ns)  
✔ Zero DRC violations  
✔ Zero shorts & opens  
✔ Antenna clean  
✔ Signoff-ready GDSII generated  

---

#  Major Engineering Challenges Solved

### 1️ Unconstrained Endpoints in Synthesis
- Identified latch-based endpoints
- Verified using `report_cell`
- Cleaned timing analysis before compile

### 2️ Macro Vertical Clustering Issue
- Initial congestion overflow: 2.5%
- Modified aspect ratio and core sizing
- Reduced congestion to 0.2%

### 3️ Power Grid DRC & Missing Vias
- Debugged using `check_pg_drc`
- Fixed via stacking and strap pitch
- Achieved clean PG connectivity

---

#  Final Signoff Status

- Setup WNS: +0.02ns
- Hold WNS: +0.28ns
- DRC: 0
- Shorts: 0
- Opens: 0
- Antenna Violations: 0

Design successfully achieved timing closure and physical verification at 28nm.

---

#  Key Technical Skills Demonstrated

- Timing-driven synthesis and optimization
- Macro-aware floorplanning
- Congestion reduction techniques
- Clock tree optimization & skew balancing
- Setup & hold timing closure
- Power grid debugging
- Full RTL-to-GDSII flow execution

---

#  Repository Structure


