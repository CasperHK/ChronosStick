# ChronosStick (`circuit.tsx`)

**ChronosStick** is a nano-sized USB hardware time synchronizer designed using **tscircuit** (Code-First Electronics). By combining a low-power microcontroller with a micro GNSS module, it captures hardware-level 1PPS (Pulse Per Second) signals to provide microsecond-level local time synchronization for servers and host machines.

---

## 🌟 Key Features

* **Code-First Hardware Design**: Entirely defined using TypeScript/TSX, enabling seamless version control, automated PCB layout, and schematic generation via `tscircuit`.
* **Ultra-Compact Form Factor**: Engineered to match the size of a standard USB flash drive (**18mm x 45mm**), making it ideal for space-constrained server racks.
* **Hardware-Level Precision**: Directly connects the GNSS module's 1PPS output to a hardware interrupt pin on the MCU, eliminating OS-level jitter.
* **One-Button Sync**: Features an integrated tactile switch to trigger instant force-sync commands or toggle status diagnostic modes.
* **Native USB Interface**: Acts as a standard USB CDC or HID device for effortless host communication without bulky bridge chips.

---

## ⚙️ How It Works

1. **Satellite Acquisition**: Upon plugging into a host USB port, the onboard GNSS module acquires UTC time and locks onto satellite signals.
2. **Pulse Capture**: The microcontroller monitors the hardware 1PPS signal to timestamp exact second edges with microsecond accuracy.
3. **Host Synchronization**: The device transmits high-precision time data via USB, integrating smoothly with host daemons (such as Linux `chrony`) for smooth clock slewing.
4. **Interactive Control**: Pressing the physical button forces an immediate time-sync packet transmission or cycles through operational status displays.
