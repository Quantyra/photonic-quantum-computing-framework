# Getting started and integration

This guide describes a provisional mechanical integration and a basic detector commissioning procedure. Read the component instructions before printing, wiring or powering hardware. Dimensions below are nominal CAD values in millimetres. Package fit, retention, alignment, electrical safety and optical response require physical checks.

## Obtain the authoritative parts

Use the [jig v11.1.2 source snapshot](https://github.com/Quantyra/photodiode-jig/tree/d7c9fc1ea49c0633ac80b1acda1bc9f219ac0a4f) and the [optical fixture system](https://github.com/Quantyra/optical-fixture-system). Use the released [fixture v1.0.1 archive](https://doi.org/10.5281/zenodo.23485390) and [exact source snapshot](https://github.com/Quantyra/optical-fixture-system/tree/896505162a5071a4d7b6152c34f7ddb40a4cb497), commit `896505162a5071a4d7b6152c34f7ddb40a4cb497`; record the selected stand and paths before fabrication. Follow its [print and assembly guide](https://github.com/Quantyra/optical-fixture-system/blob/896505162a5071a4d7b6152c34f7ddb40a4cb497/docs/print-and-assembly.md), [G-code notes](https://github.com/Quantyra/optical-fixture-system/blob/896505162a5071a4d7b6152c34f7ddb40a4cb497/gcode/README.md) and [supplied STLs](https://github.com/Quantyra/optical-fixture-system/tree/896505162a5071a4d7b6152c34f7ddb40a4cb497/stl).

The jig's authoritative [dual-port guide](https://github.com/Quantyra/photodiode-jig/blob/d7c9fc1ea49c0633ac80b1acda1bc9f219ac0a4f/designs/v11/dual-port/PRINT_SIMPLE_V11.md), [single-port guide](https://github.com/Quantyra/photodiode-jig/blob/d7c9fc1ea49c0633ac80b1acda1bc9f219ac0a4f/designs/v11/single-port/PRINT_SINGLE_V11.md), and [Arduino wiring/upload guide](https://github.com/Quantyra/photodiode-jig/blob/d7c9fc1ea49c0633ac80b1acda1bc9f219ac0a4f/docs/arduino-setup.md) govern their respective parts. Download the logger from that repository; do not substitute code from an unrecorded revision. Reslice authoritative STLs for your machine; review component G-code limitations before any reuse.

## Bill of materials and roles

| Item | Quantity / role | Selection check |
| --- | --- | --- |
| V11 dual holder, matching front shutter, matching rear drawer | One each; two detector ports and four marked states | Use one variant's complete set; single/dual panels are not interchangeable |
| Photodiodes | Two for dual, one for single | Identify actual model, dimensions and datasheet K/A pinout; published fit is not universal |
| Source stand | One, preferred 34 x 28 mm foot; supported narrow option 32 x 28 mm | Measure LED body/flange, lead section, usable lead lengths and allowed forming procedure before fitting |
| Detector cradle | One, 50 x 32 mm foot | Designed for complete dual V11 shell, leads upward; single-jig cradle compatibility is not established |
| Ambient hood | One, 90 x 90 x 110 mm clear interior | Lift-off ambient cover; actual clips, cables, fit and shielding need checking |
| Opaque, rigid, flat board and nonconductive fixing material | One common support | Fix fixtures independently, preserve equal support height and panel access |
| Low-power source LED, supply and appropriate current limiter | One independent source circuit | Choose resistor/driver from actual LED and supply ratings; measure current before use; no bare LED across supply |
| Classic Nano or Uno, USB data cable | One 5 V ATmega328P board | Other board families require a separately validated setup |
| 10 kohm resistors, insulated wiring/breadboard | Two independent detector loads for dual | Shared ground only at resistor bottoms; keep signal nodes separate |

This fixed fixture is intended for a low-current IR LED setup. The public logger guide's generic baseline uses a low-power visible source. Record and separately commission any change to IR, source device or geometry. No source current, diode polarity, part identity or supply rating can be inferred from fixture colors or CAD proxies. Lasers, UV and high-voltage SPAD wiring are outside this guide.

## Print and inspect

- **Jig:** import in millimetres at 100%, preserving supplied orientation. The dual holder prints on its x-end/side, 44 mm tall, not in bench orientation; panels print flat with grips/engraving or retaining lands up. The single holder is 34 mm tall in print orientation. PETG Normal 0.20 mm, supports off, 5 mm outer holder brim are starting guidance. Inspect rails, bridges, lead exits and panel features in the slicer. Follow the selected variant guide for details.
- **Source stand:** print foot-down as exported, with the correct PETG material/machine profile, 0.4 mm nozzle and 0.2 mm layers; about three walls and suitable infill are starting guidance. Supports off follows CAD roof geometry, not physical validation. Inspect the separate grooves, separating web, bore, flange seat and floor. Do not scale to force a package fit.
- **Cradle:** print flat foot-down as exported using the component's PETG guidance; inspect floor and fixed-body tabs. Preserve its geometry and the jig's panel corridors.
- **Hood:** print closed roof on the bed and open rim upward, not in installed orientation. PETG, 0.4 mm nozzle, 0.2 mm layers, supports off by geometry; optional 5 mm brim. Outer bounds are 94 x 94 x 112 mm, or 104 x 104 mm in plan with that brim. Verify actual machine envelope, adhesion and layer preview. User reports printing well after PETG profile correction; this is not an assembled fit or shielding test.

Use your actual PETG profile rather than assuming a generic material preset is equivalent. Remove defects without damaging thin features. Inspect and dry-fit without forcing packages or straining leads. Black PETG appearance does not establish IR opacity.

## Assemble and establish geometry

1. Assemble the jig and its matching shutters according to its guide. Check all marked states and full drawer removal. The dual guide describes lead exits down; the cradle mounting reverses that pose. Seat the complete dual jig on its fixed lower shell edges in the cradle, **lead exits upward**, light-entry face toward the source. The nominal aperture/source optical axis is 20 mm above the common board. Confirm actual height after fixing materials are compressed.
2. Fit the measured source component gently. Form leads only with suitable independent support near the package, within its manufacturer's requirements; never bend against the installed package or use the printed corner as a forming tool. The stand has rear-open separate grooves and a recessed flange seat. Confirm both leads reach the intended insulated terminations without tension; tape is not proof of retention. Keep bare leads apart, insulate joints and strain-relieve relaxed tails to the board.
3. Place the source front foot against the source-facing cradle foot. The proposed butted layout has no self-locking locator. Fix both feet to the same opaque rigid board, with equal compressed fixing thickness. Fix only the jig's solid stationary body if additional retention is needed; keep tape off shutters, windows and lead exits. Verify shutter movement does not shift either fixture.
4. Choose one alignment and keep it fixed for a run block. For the dual jig, the **fixed body** is 44 mm wide and port pitch is 10 mm. The source foot is 34 mm wide: 44 - 10 = 34. Matching left corresponding edges puts the source center at X=-5 relative to body center; matching right edges puts it at X=+5. Centering gives X=0. Reference the fixed jig body, not the 50 mm cradle or projecting panels. Left/right here are assembly coordinates; the cradle pose reverses the original jig X axis. Verify actual electrical channels physically. Edge alignment does not guarantee illumination of only one port.
   The supported [32 mm narrow stand](https://github.com/Quantyra/optical-fixture-system/blob/896505162a5071a4d7b6152c34f7ddb40a4cb497/stl/source_stand_32mm.stl) requires separately measured lateral placement: same-edge registration against the 44 mm body gives a 6 mm offset, rather than the port center at 5 mm. This 32 mm STL has no current G-code and requires re-slicing. Current stand G-code is dimensionally consistent with the preferred [34 mm stand](https://github.com/Quantyra/optical-fixture-system/blob/896505162a5071a4d7b6152c34f7ddb40a4cb497/stl/source_stand_34mm.stl); exact source slicing is not established. Re-slice the selected STL for your machine and material.

5. The source axis and seated apertures nominally share Z=20. With butted feet, the modeled lens-to-front-shutter broad surface gap is **18.2 mm**, not a measured working distance (lens-to-outer guide is 16.2 mm). Measure the actual lens endpoint, distance and alignment; do not silently reuse a run commissioned at another distance. A centered source is an alternative geometry requiring its own commissioning. The single jig's fixed body is 34 mm wide, so same-edge registration would center the source, but this does not establish compatibility with the dual cradle.
6. Check retention, relaxed cables and all shutter states with the hood removed. Leave full withdrawal corridors clear; resting-state clearance does not provide hand or panel-removal space.

## Hood and cable routing

The independent hood rests on the board, enclosing the source, detector and free-space path; keep the Arduino and source switch outside. Its 90 x 90 x 110 mm interior accommodates a modeled 88 mm hardware envelope plus 22 mm relaxed-wire allowance. The clips and wire bundle are illustrative: measure your actual arrangement, and ensure the cover never presses on clips, packages or wires.

Use the offset bottom-open rear cable exit and integral baffle: route relaxed cables left around the baffle end, then right along the rear channel to the notch. Lift the hood to lay cables into the notch; clips need not be threaded through it. Check actual bundle fit and strain. **Remove the hood before shutter movement or panel withdrawal.** Place it back without shifting fixtures.

The board is the floor. Inspect bottom gaps and the cable exit; removable opaque tape outside a seam may be explored. CAD clearance and straight-ray obstruction do not prove light exclusion, diffuse leakage performance or wall opacity. Practical assembled fit and shielding remain pending. This is an ambient hood, not a laser safety enclosure.

## Wire and commission

Use the [authoritative Arduino guide](https://github.com/Quantyra/photodiode-jig/blob/d7c9fc1ea49c0633ac80b1acda1bc9f219ac0a4f/docs/arduino-setup.md) and its circuit diagram exactly. Power off for wiring changes. In that reference, verified photodiode cathodes connect to board **3.3 V, not 5 V**; anodes/signals connect separately to A0 and A1, each with its own 10 kohm load to GND. Leave AREF unconnected. Confirm actual polarity from the actual diode datasheet. Viewed from the source, the intended mapping is A0/right and A1/left; check it by illuminating/blocking each port. Do not infer mapping from colors or the reversed CAD pose.

The Classic 5 V ATmega328P board's 10-bit ADC reports nominal 0-1023 counts. The logger's voltage estimate assumes a 5.0 V AVcc reference, separate from the 3.3 V diode bias; it is not calibrated irradiance. A0 and A1 are sequential averages, not simultaneous measurements. For single-port use, follow the guide's unused-A1 termination instructions and ignore its columns.

1. Before source use, verify its independent current limiter, rated wiring and insulation; measure source current with suitable equipment and confirm it is within the actual component's ratings. Record device identity, supply, limiter, current and settings. The logger does not control the source or record shutter states.
2. Record component versions/commits, print material/profile, actual geometry, board/reference assumptions, resistor values, diode identities/polarities and channel mapping. Check for shorts with power removed, then inspect powered readings for unstable wiring, clipping, compression or unexpected zero/full-scale values. Check each port independently.
3. Establish a **source-off dark control**, recording aperture states and settling time. With source off and apertures open, compare room lights on/off and positions to investigate ambient leakage through wall, seams and cable exit. Separately assess IR wall transmission against an opaque reference at controlled geometry and suitable detector sensitivity before claiming shielding. No acceptance threshold or measured attenuation is supplied here.
4. Follow the jig guide's **B00 source-on, both-blocked baseline** (single: CLOSED), then **B01-B03** repeated state sequences with fixed source setting, geometry, dwell and settling intervals. Keep the source-off dark control distinct from B00. Record state labels and row ranges externally; discard transitions. Lift the hood for each change and check that replacement does not disturb geometry.
5. Compare baselines and repeats for drift, leakage, clipping and fixture movement. Recommission after any alignment, source, distance or wiring change; keep changed geometries separate in records. These are handling/readout checks, not calibration, proof of optical isolation or evidence of quantum computation.

For citations, changes or additional components, see [CONTRIBUTING.md](../CONTRIBUTING.md).
