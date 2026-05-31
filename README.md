 C-Clicker v3.0

### 🏢 Deep Economy & Building Tiers
Features **10 unique building types** spanning across historical and sci-fi themes:
* **Production Tiers:** From humble `Cursors` and `Grandmas` to advanced `Wizards`, `Spaceships`, and `Alchemy Labs`.
* **Exponential Scaling:** Costs scale dynamically using a classic incremental formula (Cost = BasePrice * 1.15^Owned), capped safely at 5,000 units per building.

### ⚡ Dynamic Active Gameplay Elements
* **Click Combo System:** Fast manual clicking triggers an active combo meter. Maintaining the rhythm scales up your click power continuously (+5% click power per combo level).
* **Golden Cookies:** Randomly spawns lucky elements across the screen, triggering powerful **Frenzy periods (7x CpS for 30 seconds)** upon collection.
* **Special Boosts & Global Events:** Features timed event multipliers (e.g., *Sugar Rush*, *Bakery BOOM!*, *Cookie Rain*) alongside purchasable active boosts to break production ceilings.

### 🌌 Prestige & Ascension System
When progression slows, players can trigger an **Ascension**. 
* **Heavenly Chips:** Earned based on a strict mathematical progression: cube_root(Total Cookies / 1,000,000).
* **Persistent Multiplier:** Each Heavenly Chip permanently boosts your Cookies per Second (CpS) by **+1%** in the next life cycle.

### 🏆 Achievements & Quest Matrix
* **Milestone Tracking:** Includes an array of progression-based achievements monitoring click rates, raw wealth tiers, collection completion, and maximum combo ceilings.
* **Reward-driven Quests:** Active sub-objectives that reward massive cookie payouts to accelerate mid-game progression.

---

## 🛠️ Advanced Technical Architecture

### ⚡ High-Performance Game Loop (`requestAnimationFrame`)
Unlike standard incremental games that rely on unstable `setInterval` timers, Crazy Clicker utilizes the native browser animation frame framework.
* Synchronizes logic steps directly with the client monitor's refresh rate.
* Dynamically calculates delta time (`deltaTime`) to ensure smooth, uniform background execution even during frame drops or tab unfocusing.

### 📉 DOM Layout Thrashing Mitigation (UI Caching Engine)
Writing to the DOM repeatedly kills browser rendering performance. This architecture solves layout thrashing by implementing a **virtual UI string cache**:
* Values (Cookies, CpS, Combos) are formatted and cross-checked against a central cache object (`uiCache`).
* The browser DOM textContent is *only* modified if the newly computed string differs from the previous tick.

### 💾 Obfuscated Local Storage State Persistence
* **Auto-Save Engine:** Features an automatic state-saving system that executes every 30 seconds.
* **Data Integrity Protection:** To mitigate trivial clear-text state tampering via browser developer tools, save data objects are JSON-stringified, safely URL-encoded, and obfuscated using **Base64 binary-to-text encoding** (`btoa` / `atob`) with automated legacy clear-text fallbacks.

---

## 🕹️ Getting Started / Installation

As a pure client-side vanilla web application, the game requires **no compilation, no Node.js dependencies, and no web server installation**.

1. Clone or download this repository.
2. Double-click the `cookieClicker.html` file to run it directly in any modern desktop web browser (Chrome, Firefox, Edge, Safari).
