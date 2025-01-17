java c
MENG 4019 - Practical 2 – 2022
Task: design and simulate the operation of an electro-hydraulic curcuit. A hydraulic cylinder, stroke 2000 mm, D piston 100 mm, d rod 50 mm angled 60 degrees from horizontal is lifting a mass load of 6000 kg, with a push external force of 10 kN and pull external force of 6 kN. The cylinder needs to extend/retract as needed. Manually, then controlled by an electrical circuit.
First, we build a conceptual circuit:
1. Open Automation studio, select and insert the following components from the Hydraulic set of components

2. Click on Filter to select, Right click on Filter, click on Lock Size to unlock, reduce size of Filter (drag it to a smaller size), Right Click on Filter, click on Lock Size to lock

3. Connect circuit as shown below:

4. Select the Simulation tab and run a Normal Simulation. Then, Stop Simulation and run a Slow-Motion Simulation

5. This shows that the circuit is correct, and it works. The cylinder can extend and retract, s needed. The components are all connected, there is no error reported by the system. The flows and pressures are consistent with the settings of the components.
6. We need to modify the control of the valve, to change it from a manual control to a solenoid. Double click the valve and select Technical Specifications from the left lower tab.

Then, double click on the manual lever, select solenoid and confirm selection

Using the arrows from the top, center the solenoid to the middle of the valve:

7. Start creating the electric control circuit. From the Electrical Control (JIC Standard), insert the power source (24 V and 0 V), the start button (push button, name it START) and a solenoid (call it SOL). Connect the components.

8. We see that the hydraulic circuit works (we can change the position of the valve manually), and the electrical circuit works – we can test by clicking on the Push Button (START). But the two circuits are not connected.
9. We need to connect the two circuits
Double click on the Valve. Select Variable Assignment from the left lower tab. Connect the solenoid of the valve with the solenoid from the electric circuit (SOL)

Double click on SOL on the top right panel. The two solenoids代 写MENG 4019 - Practical 2 – 2022
代做程序编程语言 are connected (common name):

NOTE: make sure the valve is not in the manual control position:

If this is the case, click on the solenoid, the red tick in the valve disappears and the circuit can be controlled electrically. Now, if you press the START button, the valve switches:

10. Adjust details of the actuation based on the given data:

You can rotate the cylinder to reflect the details of the problem – right click on cylinder and select Coordinates and Orientation:

11. We want to ensure that, once we press the START button, it will continue to work without having to keep it pressed. We insert a normally open contact that we connect to the solenoid and a coil:

We make the connections. We check the circuit. It works:

However, we want to be able to reverse when we need. We insert a Normally Closed Push Button, and we check the circuit. It works:

12. We want to insert a small automation in the circuit so that, when the cylinder reaches the end, the solenoid is de-energised, and the piston is retracting. We need to insert a Proximity Sensor at the end of the stroke.
Insert a proximity sensor (call it A1), rotate it 60 degrees and place it at the max stroke of the cylinder (extend it to 100% to facilitate placement):

13. Add a Normally Closed Proximity Switch from the Electrical Control (JIC Standard) and link it to the Proximity Sensor A1

Check that the circuit works. All seems correct:

14. We want to automate the circuit so that once we start it, it will extend, retract and continue the cycle until we stop it. We need another Proximity Switch and we need to integrate it in the circuit:
Due to the grid resolution, it is difficult to select the exact position of the cylinder we want (0 and 100% extension, so we revert to the normal position of the cylinder.
We insert another Proximity Switch on the cylinder and a Normally Open Proximity Switch in the circuit. We link it to A0.

We check that it works. All is correct, except the system only runs one cycle and stops.
15. We replace the START Push Button with a Normally Open Toggle Switch. We check that it works. All is working as expected:






         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
