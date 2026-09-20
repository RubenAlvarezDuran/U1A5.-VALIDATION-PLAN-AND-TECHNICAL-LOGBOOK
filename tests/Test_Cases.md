# SCARA Robot - Initial Test Cases



## TC-01 - Homing and Limit-Switch Test

**Objective:** Verify that the robot establishes a repeatable reference position and stops safely at each configured limit.

**Initial conditions:** Robot powered on; axes positioned away from home; limit switches connected; electromagnet OFF.

**Procedure:** 1) Start the homing routine. 2) Observe each axis moving toward its switch. 3) Verify that motion stops when the switch activates. 4) Repeat 10 times from different initial positions. 5) Measure the final home position.

**Expected result:** All three axes reach home without collision and the final reference position is repeatable.

**Pass/Fail criterion:** PASS if every cycle completes correctly and the final reference position remains within +/-1 mm.



## TC-02 - Point-to-Point Positioning Test

**Objective:** Evaluate positioning accuracy at representative points in the SCARA workspace.

**Initial conditions:** Robot homed; no payload or standard test payload installed; reference grid fixed to the work surface.

**Procedure:** 1) Home the robot. 2) Command five predefined XY/Z target positions. 3) Measure actual end-effector position. 4) Repeat each point three times. 5) Record absolute error.

**Expected result:** The end effector reaches each commanded point with small and repeatable error.

**Pass/Fail criterion:** PASS if the maximum absolute position error is <= 3 mm at every test point.



## TC-03 - Power Consumption Test

**Objective:** Verify that the 12 V / 6 A power architecture supports normal robot operation without excessive current draw or voltage instability.

**Initial conditions:** Multimeter or DC power meter connected at the 12 V input; robot homed; representative payload available.

**Procedure:** 1) Measure idle current. 2) Run simultaneous/representative axis motion. 3) Activate the electromagnet during the cycle. 4) Record normal and peak current. 5) Observe for ESP32-S3 resets or driver faults.

**Expected result:** The system remains stable and current stays within the power-supply capability.

**Pass/Fail criterion:** PASS if normal current is < 5.0 A, peaks remain < 6.0 A, and no controller reset occurs.



## TC-04 - Electromagnet Pick-and-Place Test

**Objective:** Verify reliable pickup, transport, and release of the selected ferromagnetic part.

**Initial conditions:** Robot homed; test piece placed at the defined pickup location; electromagnet and MOSFET stage connected.

**Procedure:** 1) Move to pickup point. 2) Activate electromagnet. 3) Lift and transport the part. 4) Move to drop point. 5) Deactivate electromagnet. 6) Repeat 20 times.

**Expected result:** The robot completes the pick-and-place sequence without dropping the part and releases it at the target.

**Pass/Fail criterion:** PASS if at least 19 of 20 cycles are successful.



## TC-05 - Continuous Stability Test

**Objective:** Verify stable operation during repeated robot cycles.

**Initial conditions:** Robot homed; normal firmware loaded; normal payload and power supply connected.

**Procedure:** 1) Run 20 complete automatic cycles. 2) Monitor serial messages and physical position. 3) Record resets, false limit events, lost steps, overheating, or unexpected stops.

**Expected result:** The robot completes all cycles with consistent position and no critical fault.

**Pass/Fail criterion:** PASS if all 20 cycles finish without reset, uncontrolled motion, or observable lost-step error.

