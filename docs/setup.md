# Wiring and KK2.1 setup notes

Notes I kept while putting the quadcopter together, so I don't have to dig through the slides again.

## Wiring

- The four A2212 motors sit at the ends of the F450 arms. Each motor goes to its own 30A ESC.
- All four ESCs are powered in parallel from the LiPo through the power distribution board on the F450 bottom plate.
- ESC signal leads go to M1, M2, M3 and M4 on the KK2.1 board.
- Two motors spin clockwise and two spin anti-clockwise so the torque cancels out. The KK2.1 shows the motor order and spin direction for the selected layout on its screen, so match the props to that.
- Receiver to KK2.1 inputs:

| Receiver | KK2.1 input |
|----------|-------------|
| CH1 | Aileron (roll) |
| CH2 | Elevator (pitch) |
| CH3 | Throttle |
| CH4 | Rudder (yaw) |

- Only one of these four leads carries Vcc and Gnd to the board. The other three are connected with just the signal wire.
- The servo for the delivery box goes straight into the receiver on one of the leftover channels, so it is controlled from the transmitter and doesn't go through the flight controller.

## KK2.1 setup order

This is the order we went through the menus after powering on:

1. Load Motor Layout and pick Quadcopter X mode
2. ACC calibration (board kept flat)
3. Receiver Test, check every stick moves the right way
4. PI Settings
5. Mode Settings
6. Misc Settings
7. ESC calibration
8. Arm and test hover

## Things that went wrong

- After setting up the board the transmitter commands were not reaching the quad. Fixed it by setting each transmitter channel separately from the PC with the FlySky software.
- With 10x4 props it was not stable, so we went down to 8x4.5 props.

## Thrust to weight

Total thrust from the four motors is about 2600 g and the whole quad weighs about 1300 g, so the thrust to weight ratio is 2:1. It can still fly at around 1.5:1 but then there is very little margin for the payload.
