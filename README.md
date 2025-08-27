<div align="center">
  <h1>
    <img src="https://github.com/4khilx/FFlag-Guide/blob/main/assets/Bloxstrap.png" width="30" /> Advanced FFlag Guide
  </h1>
</div>

<details>
  <summary><h3><strong>FFlag Basics</strong></h3></summary>

  <h2>What are fflags?</h2>
    <b>Roblox Fast Flags are configuration settings used internally by Roblox engineers to quickly enable or disable features and functionalities within the Roblox platform. These flags allow developers to test new features, make updates, and address issues without needing to deploy a full update to the platform.</b>
    
---

  <h2>How can I make fflags?</h2>
<b>You simply cannot make fflags</b> since only Roblox engineers can create them. <b>You can only find them!</b>

---

  <h2>How do I use them?</h2>
These fflags can be enabled by using a bootstrapper <b>(such as Bloxstrap)</b>, though you can simply find the file name "ClientSettingsApp.json" within your Roblox player directory and manually add the fflags there.

---

  <h2>Will I get banned?</h2>
No, you cannot have your Roblox account banned or terminated from using fflags, neither are using a bootstrapper such as Bloxstrap, Roblox staff have confirmed this (though they don't recommend using). You can otherwise get banned in a Roblox experience itself, as if you are blatantly using abusive fflags (noclip, XRay, speed hack) they can sometimes moderate this and ban you.

---

  <h2>How do I check if a fast-flag is fake or real?</h2>
  
  You can by using `flagstate` to check if a fast-flag is real and going into this game and testing your fast-flags!
- [Bloxstrap testing area VC](https://www.roblox.com/games/16627479038/Bloxstrap-testing-area-VC)
- [Desync Playground](https://www.roblox.com/games/11746390170/Desync-Playground)

</details>

<details>
  <summary><h3><strong>Advanced FFlag Guide</strong></h3></summary>

<h2>Quick Navigation</h2>

> - [**Fastflag Configuration Prefixes**](https://github.com/4khilx/FFlag-Guide/tree/main?tab=readme-ov-file#fastflag-configuration-prefixes)
> - [**Acronyms**](https://github.com/4khilx/FFlag-Guide/tree/main?tab=readme-ov-file#acronyms)
> - [**Flag Headers**](https://github.com/4khilx/FFlag-Guide/tree/main?tab=readme-ov-file#flag-headers)
> - [**Streaming Snake Case FFlags VS Pascal FFlags**](https://github.com/4khilx/FFlag-Guide/tree/main?tab=readme-ov-file#streaming-snake-case-fflags-vs-pascal-fflags)
> - [**Language Types**](https://github.com/4khilx/FFlag-Guide/tree/main?tab=readme-ov-file#language-types)
> - [**Bit Fastflags**](https://github.com/4khilx/FFlag-Guide/tree/main?tab=readme-ov-file#bit-fastflags)
> - [**Studio Fastflags**](https://github.com/4khilx/FFlag-Guide/tree/main?tab=readme-ov-file#studio-fastflags)
> - [**Rendering Modes and Which are the Best?**](https://github.com/4khilx/FFlag-Guide/tree/main?tab=readme-ov-file#rendering-modes-and-which-are-the-best)
> - [**Roblox Client Debug Menu Keybinds**](https://github.com/4khilx/FFlag-Guide/tree/main?tab=readme-ov-file#roblox-client-debug-menu-keybinds)
> - [**Common Misconceptions with FFlags and Bootstrappers**](https://github.com/4khilx/FFlag-Guide/tree/main?tab=readme-ov-file#common-misconceptions-with-fflags-and-bootstrappers)

---

<h2>Fastflag Configuration Prefixes</h2>

### `DFFlag`
> **Dynamic Fast Flag**
> - **Type:** Boolean (`true/false`)
> - **Description:** A dynamic flag that can be modified during runtime. It automatically updates every 5 minutes, reflecting any changes made to it.

### `FFlag`
> **Fast Flag**
> - **Type:** Boolean (`true/false`)
> - **Description:** A static flag that is initialized once and does not change throughout the session. It remains constant until a new session begins.

### `FInt`
> **Fast Integer**
> - **Type:** Integer (`-2147483648` to `2147483647`)
> - **Description:** A static integer that is initialized once and remains unchanged throughout the session. It only updates when a new session starts.

### `DFInt`
> **Dynamic Fast Integer**
> - **Type:** Integer (`-2147483648` to `2147483647`)
> - **Description:** A dynamic integer that can be updated during runtime. It refreshes automatically every 5 minutes to reflect any changes.

### `FLog`
> **Fast Log**
> - **Type:** Boolean (`true/false`) or Integer (`-2147483648` to `2147483647`) or Byte (`Warning, Verbose, ect`)
> - **Description:** A static log variable that is initialized once and does not change until a new session. It remains constant until the session is reset.

### `DFLog`
> **Dynamic Fast Log**
> - **Type:** Boolean (`true/false`) or Integer (`-2147483648` to `2147483647`) or Byte (`Warning, Verbose, ect`)
> - **Description:** A dynamic log variable that can change during runtime. It automatically refreshes every 5 minutes to reflect any updates made.

### `FString`
> **Fast String**
> - **Type:** String (`text`)
> - **Description:** A static string variable that is initialized once and remains unchanged throughout the session. It does not update until a new session starts.

### `DFString`
> **Dynamic Fast String**
> - **Type:** String (`text`)
> - **Description:** A dynamic string that can be updated during runtime. It automatically updates every 5 minutes to reflect any changes made.

### `SFFlag`
> **Synchronized Fast Flag**
> **Type:** Boolean (`true/false`) or Integer (`-2147483648` to `2147483647`)
> **Description:** A synchronized flag variable that is loaded by the server and sent to the client. It ensures that the flag’s state is consistent across different clients. The flag's value is forced by the server and cannot be changed by the client (you).

---

<h2>Acronyms</h2>

- **Mainly used in fastflags.**
- *Acronyms with a question mark mean they may not be correct.*

```md
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
"A" Letter Acronym FastFlags
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
Avg: Average
ACK: Acknowledge
Async: Asynchronous
Arg/Args: Argument(s)
AR: Augmented Reality
PC: Personal Computer
ABR: Adaptive Bitrate
Agg: Aggregate/Aggregation
ACS: Access Control System
AI: Artificial Intelligence
Aniso: Anisotropic Filtering
AUM: Assets under management
AABB: Axis-Aligned Bounding Box
ACE: Animation Curve/Clip Editor
Auth: Authenticate/Authentication
AES: Advanced Encryption Standard
AMC: Automated Moderation Capture
API: Application Programming Interface
APGS: Asynchronous Projected Gauss-Seidel
ASTC: Adaptive Scalable Texture Compression
ACP: Accelerated/Adaptive Collision Pipeline
AICO: Artificial Intelligence Code Completion/Asist
ATC: Asset Transaction Cache / Automatic Text Capture
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
"B" Letter Acronym FastFlags
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
BW: Bandwidth
BG: Background
BP: Blueprint (?)
BC: Block Compression
BPS: Bytes/Bits Per Seconds
BVH: Bounding Volume Hierarchy
BSP: Binary Space Partitioning
BTID: Browser Tracking/Token ID
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
"C" Letter Acronym FastFlags
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
CN: China
Cull: Culling
CPP: Cycle Plus +
CTA: Call to Action
CFM: Custom Fonts Module
CFrame: Coordinater Frame
Calc: Calculation/Calculate
CPU: Central Processing Unit
CDN: Content Delivery Network
CCD: Cyclic Coordinate Descent
CSG: Constructive Solid Geometry
CLI: Client / Command Line Interface
CFL: Courant–Friedrichs–Lewy Condition
CD: Carrier Detect/Composition Detection
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
"D" Letter Acronym FastFlags
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
DC: Data Carrier
DPI: Dots per inch
DMP: DataModelPatch
DOF: Depth of Field
DNS: Domain Name System
DB: Data Table / Database
Diff: Different / Diffraction
DCR: Developer Console Rewrite
DRM: Digital Rights Management
DRS: Dynamic Resolution Scaling
DXT: DIrectX Texture Compression (S3TC)
Diq: Data Ingestion Quota / Delay-in-Queue
DCD: Data Carrier Detection/Decomposition / Dynamic CSG Decomposition
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
"E" Letter Acronym FastFlags
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
Exec: Execute
EXP: Experience
Email: Electronic Mail
ELF: Event Logging Framework
ESEI: Event Stream Edge Ingestion
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
"F" Letter Acronym FastFlags
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
Func: Function
Freq: Frequency
FC: Fast Cluster
FV: FastVariables
FIB: Future Is Bright
FK: Forward Kinematics
FPS: Frames Per Second
FRM: Frame Rate Manager
FTUX: First Time User Experience
FSM: F: Froxel/Forward S: Shading-Shadow M: Manager-Method / Finite State Machine
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
"G" Letter Acronym FastFlags
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
GB: Gigabyte
GLC: Gui Layout Container
gIFT: GL Transmission Format
GPU: Graphics Processing Unit
GUAC: Global User App Configuration
GC: Garbage Collection / Game Content
Gma: Game Manager API / Google Mobile Ads
GJK: Gilbert–Johnson–Keerthi Distance Algorithm
GUID: UUID - Globally / Universally Unique Identifier
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
"H" Letter Acronym FastFlags
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
HDR: High Dynamic Range
HSR: Hidden Surface Removal
HTTP: Hypertext Transfer Protocol
Hz/Hertz: Measurement For Frequency
HTTPS: Hypertext Transfer Protocol Secure
HACD: Hierarchical Approximate Convex Decomposition
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
"I" Letter Acronym FastFlags
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
IAP: In-App Purchase
Iter(s): Iteration(s)
IP: Internet Protocol
Ik: Inverse Kinematics
Inc: Incoming / Income
IAS: Input Action System
ISA: Instance Class Name
IBL: Image-Based Lighting
IXP: Internet Exchange Point
iOS: iPhone Operating System
ISR: Interrupt Service Routine
IG: Intel-Integrated-Immediate Graphics
IDE: Integrated Development Environment
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
J" Letter Acronym FastFlags
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
JDI: Json Delta Interchange
JIT: Just-in-Time (Compilation)
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
"K" Letter Acronym FastFlags
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
KB: Kilobytes
KTX: Khronos Texture
KFS: Key Frame Sequence
KBpS: Kilobytes Per Second
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
"L" Letter Acronym FastFlags
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
LOD: Level of Detail
LRU: Least Recently Used
LSP: Language Server Protocol
LMKD: Low Memory Killer Daemon
LMS: Latency Measurement Service
LDL: Lower Diagonal Transpose [L: lower triangular matrix | D: diagonal matrix | L: transpose of L]
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
"M" Letter Acronym FastFlags
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
Max: Maximum
Msg: Message
MB: Megabyte
MIB: Mebibyte
Multi: Multiple
ML: Machine Learning
Min: Minutes-Minimum
Mutex: Mutual Exclusion
MPS: Market Place Service
MRS: Message Routing Service
MS/MSec/Millis: Milliseconds
MTU: Maximum Transition Unit
MMAP: Memory-Mapped File I/O
MRF: Multiple Replication Foci
MSAA: Multisampling Antialiasing
MacOS: Macintosh Operating System
MRD: Mega Replicator Data-Dictionary
MFT: Metrics-Memory-Monitoring Fault Telemetry
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
"N" Letter Acronym FastFlags
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
Num: Number
NS: NextStep
NAT: Network Address Translation
NOU: Number of Units/Network Ownership
NCNN: Neural Network Inference Framework
NLSM: Network Layer Statistics-State Monitor
NII: Natural-Language Input Inspection-Inference / Network Interpolation-Integration
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
"O" Letter Acronym FastFlags
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
OTA: Over-the-Air
OOM: Out Of Memory
OS: Operating System
OOP: Object Oriented Programming
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
"P" Letter Acronym FastFlags
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
Pkt:  Packet
Pct: Percent
Par: Particle
Poly: Polygon
Prio: Priority
Param: Parameter
Perf: Performance
PC: Personal Computer
PPJ: Price Per Job (?)
PDP: Product Detail Page
Prot: Protocol-Protection
PGS: Projected Gauss-Seidel
PBR: Physically Based Rendering
PCGDK: PC Gaming Development Kit
PD: Physics Data / Proportional-Derivative
PVS: Potentially Visible Sets / Position–Velocity Solver
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
"R" Letter Acronym FastFlags
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
Rbx: Roblox
Rcv: Receive
Rep: Replicator
RN: Rotation Number
RTT: Round-Trip Time
RTL: Right-to-Left (Arabic TXT)
Roact: Rodux-Roblox UI Frameworks
RSS: Rich Site Summary / Receive Side Scaling
RCC: Remote Chat Channel / Roblox Cloud Compute
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
"S" Letter Acronym FastFlags
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
Snd: Send
Sec: Seconds
SJ: Stream Job
SM: Static Mesh
Sim: Simulation
Stat: Statistics
SN: Scale Number
SJT: Stream Job Time
SBT: Simple Build Tool
SSL: Secure Sockets Layer
SK: Skeletal-Skeleton Mesh
Sat: Separating Axis Theorem
SSR: Screen Space Reflections
SDK: Software Development Kit
SSAA: Supersampling Antialiasing
Sync: Synchronized-Synchronization
SIMD: Single Instruction Multiple Data
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
"T" Letter Acronym FastFlags
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
TCS: Text Chat Service
TAA: Temporal Anti-Aliasing
TLS: Transport Layer Security
Thou: Thousand-Thousandths
TN: Translation (Pyhics) Number
TCP: Transmission Control Protocol
TC: Texture Compression / Team Create / Terms Compliance
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
"U" Letter Acronym FastFlags
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
Util: Utility
UX: User Experience
US/USec: Microseconds
UDP: User Datagram Protocol
UGC: User-Generated Content
URE: Unreliable Remote Event
UI: Screen UI or User Interface
URL: Uniform Resource Locator
UWP: Universal Windows Program
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
"V/W" Letter Acronym FastFlags
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
VK: Vulkan
WK: Webkit
Win: Windows
WS: Web Socket
V[Number]: Version
VR: Virtual Reality
VM: Virtual Machine
Var: Variable/Variant
VAD: Voice Activity Detection
VRAM: Video Random-Access Memory
VNG: Vietnamese-VinaGames [Vietnamese Company]
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
"Q/X/Y/Z" Letter Acronym FastFlags
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
Xbox: DirectX Box
XHR: XMLHttpRequest
QoS: Quality of Service
YUV: Y - Luma U.V - Chroma
╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍╍
```
---

<h2>Flag Headers</h2>

> 1. _IXP - Internet Exchange Point //  IP networking, allowing participant Internet service providers (ISPs) to exchange data destined for their respective networks. (not very useful)
> 2. _Staged - Replica or a Production Enviroment (not very useful)
> 3. _PlaceFilter - A filter for experiences, fastflags only work in the chosen game. // Useful to save time between switching games.
> 4. _DataCenterFilter - Similar to _PlaceFilter, a filter for datacenter IDs, only works in the chosen datacenter. // Useful for RakNet FFs.

## Example of these in fastflags:
- `DFIntS2PhysicsSenderRate_IXP` (not very useful for general use)
- `DFIntDataSenderRate_Staged` (not very useful for general use)
- `DFFlagDebugPauseVoxelizer_PlaceFilter`
- `DFIntConnectionMTUSize_DataCenterFIlter`


```json
{
  "DFFlagDebugPauseVoxelizer_PlaceFilter": "True;GameID"
}
```
```json
{
  "DFIntConnectionMTUSize_DataCenterFilter": "1472;DataCenterID"
}
```

---

<h2>Streaming Snake Case FFlags VS Pascal FFlags</h2>

`FIntSTUDIO_ENV_CHANGE_DELAY_MS`

Screaming Snake Case: `ALL_WORDS_BIG_WITH_UNDERSCORES`, used for constants (things that don’t change) to make them stand out.

Pascal Case (used by FFlags): `WordsStuckTogetherWithEachWordCapitalized`, used for names like classes or titles.

---

<h2>Language Types</h2>

  ## There are three types of flag languages

`Lua`, `C++`, and `UserFlag`. 

**`C++`** and **`Lua`** takes the majority, **`UserFlag`** takes a very small portion.

---

<h2>Bit Fastflags</h2>

- A "bit" is how much data can be processed.
- For example, 64 bit will process more data than a 32 bit.
- There is only 3 types of bits in fastflags

> - 32 Bit
> - 16 Bit
> - 8 Bit

32-bit integer: Maximum value is 2,147,483,647.
16-bit integer: Maximum value is 32,767. (roblox doesn't use this much anymore)
8-bit integer: Maximum value is 255.

These maximum values all can be checked with `flagstate`.
8 bit fastflags are generally useless and have no use.

---

<h2>Studio Fastflags</strong></h2>
  
  Studio fastflags do not work for general use and only work for **studio** (obviously).
How do you know if a fastflag is studio?

"beta", "studio", "BetaEnabled", "BetaFeature", "BetaFeatureRoleSet", "BetaFeatureRolloutPercent", "BetaFeatureUrl"
If a fastflag has these keywords, they are usually studio fastflags.

---

<h2>Rendering Modes and Which are the Best?</h2>

  These are the **rendering backends** used by Roblox on different platforms:

- **DirectX 11/10** → PC & Xbox  
- **Vulkan/OpenGL** → Android  
- **Metal** → Apple devices (iOS & macOS)  
- **Orbis** → PlayStation  

Each one handles how graphics are processed on that platform.
Which ones are the best for each platform?
Well, to say simply. The newest ones are mainly best.
If you're on PC, Dx11 is best, if you're on Android, Vulkan is best, if you're on MacOS, Metal is best.

You can still use **DirectX** and **Vulkan** on PC, both are supported renderers.  
**DirectX11** is enabled by default for most windows users, but **Vulkan** can be enabled manually or through certain flags for testing or compatibility. **Metal** and **Orbis** are exclusive to apple and playstation systems, so they can’t be used on PC.

---

<h2>Debugging FFlags</h2>

```json
{
"FLogDebugShowFlagState": "FLAG_HERE"
}
```
> ### Ex.
```json
{
 "FStringDebugShowFlagState": "DFIntTaskSchedulerTargetFps, ChannelName"
}
```
## WATCH THIS VIDEO TO LEARN MORE
https://youtu.be/USzEqHQ_87g?si=7OKCsGp3DPAad-yF
Made by DrPlaguestien

---

<h2>Roblox Client Debug Menu Keybinds</h2>

| **Action**             | **Windows**              | **Mac**                   | **Mobile**                                    |
|-------------------------|--------------------------|---------------------------|-----------------------------------------------|
| *Game stats*           | `Shift + F1`             | `Fn + Shift + F1`         | None                                          |
| *Graphics stats*       | `Shift + F2`             | `Fn + Shift + F2`         | None                                          |
| *Network stats*        | `Shift + F3`             | `Fn + Shift + F3`         | None                                          |
| *Network diagnostics*  | `Ctrl + Shift + F3`      | `⌘ + Fn + Shift + F3`     | Double-tap *"Joining game"* while loading     |
| *Network debugging*    | `Shift + F3`, then `Shift + 1` | `Fn + Shift + F3`, then `Shift + 1` | None |
| *Physics stats*        | `Shift + F4`             | `Fn + Shift + F4`         | None                                          |
| *Summary stats*        | `Shift + F5`             | `Fn + Shift + F5`         | None                                          |

---

<h2>Common Misconceptions with FFlags and Bootstrappers</h2>

> 1. Fastflags can NOT reduce ping.
> 2. Some fastflags can be abusive but they are NOT hacking tools, no fflag can give you better hitbox or allow you to fly.
> 3. Fastflags are Roblox code, they can boost FPS, but they are not originally meant to boost FPS.
> 4. You can use fastflags without a bootstrapper like Bloxstrap, it's called ClientAppSettings.
> 5. All bootstrappers do relatively the same thing, no bootstrapper can give you more FPS.
> 6. Big lists does NOT mean more performance, dumping random flag lists from the internet can break features, cause visual glitches, or lower performance.
> 7. FFlags work on ALL bootstrappers. Some fastflags don't work on specific **platforms.**
> 8. Certain fastflags are not required to be set to your number of CPU cores/logical processors, those are just recommended to set them to. (DFIntRuntimeConcurrency, FIntTaskSchedulerAsyncTasksMinimumThreadCount)
> 9. Fastflags can not get you closer to your regions.
> 10. Adding default values to your flag lists will not do anything. (Example: Setting DFIntMaxFrameBufferSize to 10 will reduce latency, this is FALSE)
> 11. FFlags are NOT the solution to your problems, they are useful but will not save your FPS issues. They are a temporary fix.
> 12. Roblox does NOT accept decimals.
> 13. Dont rely on AI to create lists for you.
> 14. 90% of FFlag's dont have a meaningful impact on normal gameplay.

</details>

<details>
  <summary><h3><strong>Sites for finding fastflags</strong></h3></summary>
  
- [**FVariables**](https://raw.githubusercontent.com/MaximumADHD/Roblox-Client-Tracker/roblox/FVariables.txt)  
- [**PC Desktop Client**](https://raw.githubusercontent.com/MaximumADHD/Roblox-FFlag-Tracker/main/PCDesktopClient.json)  
- [**PC Client Bootstrapper**](https://raw.githubusercontent.com/MaximumADHD/Roblox-FFlag-Tracker/main/PCClientBootstrapper.json)

</details>

<details>
  <summary><h3><strong>Best Discord Bots/Apps for fastflags</strong></h3></summary>

- [**Scrooms Utility**](https://discord.gg/84jKZcdQ2B)
- [**Flemish FFlags**](https://discord.gg/UHfwyxjeya)

</details>

<details>
  <summary><h3><strong>Fastflag Tips/Explanations</strong></h3></summary>

> 1. Having overlays can actually harm FPS, so yes. `FFlagDebugDisplayFPS` can actually reduce FPS.
> 2. Debug fastflags, usually have something to do with UI or quality. For example, `DFIntDebugFRMQualityLevelOverride` and `FFlagDebugAdornsDisabled`
> 3. DX11 is more performant than DX10 because of its optimizations, better swapchain, and e2e latency. You shouldn’t base it off visuals.
> 4. Most integer fastflags have a default value of -1, that default value cancels out the effects, for example: (DFIntDebugDynamicRenderKiloPixels, FIntRomarkStartWithGraphicQualityLevel)
> 5. Anything can be added to an FString.
> 6. Disabling **all** `telemetry`, will not do anything in terms of performance. It will also cause visual and other bugs.
> 7. `DFIntDebugFRMQualityLevelOverride` when set at value 1, handles MSAA and PostFx.
> 8. Default MTU size (1396) is the best in 99% of all situations.
> 9. FLogDebugShowFlagState is 90% correct; it only turns 100% correct when you join a game.
> 10. Using ping flags, could actually cause instability in some cases. Using ping fastflags is not going do anything anyways, ROBLOX has these settings already on a default value that shouldnt be touched.
> 11. Sometimes you just won't be able to understand fastflags, the names of fflags are usually weird programming language. (Refer to Acronym section)
> 12. If your going to create your own flag list, only use flags which you what they do.
> 13. No fastflags are made for certain games (except placefilter fflags used mainly by admins) though some fflags can help certain games, which is usually marginal.
> 14. Roblox is limited to one core. It uses a single main thread called the green thread.
> 15. Please dont spam fflag lists together or it will worsen your fps.
> 16. No texture will do nothing on high end PC.
> 17. Fastflags are useful, but don't except a HUGE difference, it is not a permanent solution to your FPS issues.
> 18. Fastflags can NOT reduce ping.
> 19. Roblox is mainly a CPU based game.
> 20. Using a fastflags default value will not do anything.
> 21. Reading dev forums are useful to learn, they can also correlate to fastflags. 
> 22. You can find fastflags in the Roblox Dev Console Memory.
> 23. Some fastflags have names which people falsely interpret, such as FIntTargetRefreshRate (this doesn't target refresh rate, it targets something else.), don't blindly assume stuff.

</details>

---

<div>
  <h3>Made by <a href="https://discord.com/users/1254472513199673347">Scroom</a>, <a href="https://discord.com/users/1175727303783886870">DrPlaguenstein</a>, <a href="https://discord.com/users/873383972372119574">Transaction Fraud</a>, <a href="https://discord.com/users/1286961047990702124">leventgameing</a>, <a href="https://discord.com/users/611347070648844298">M.M.</a>, <a href="https://discord.com/users/1344953953095258144">koain</a>, <a href="https://discord.com/users/1395141912339677186">arobsite</a>, <a href="https://guns.lol/4khilx">4khilx</a></h3>
</div>
