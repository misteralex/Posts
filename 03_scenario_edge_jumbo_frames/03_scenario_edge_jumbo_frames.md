---
marp: false
theme: uncover
class: invert
paginate: true
footer: '@AF'
backgroundColor: #0d1117
style: |
  .main-title {
    font-size: 0.8em;
    color: #88b6ff;
    font-weight: 800;
  }
  .extra-title {
    font-size: 1.0em;
    color: #f53e48;
    font-weight: 800;
  }
  .extra-title::before {
    content: "☕";
    margin-right: 0.25em;
    color: #800000;
    vertical-align: middle;
  }
  section {
    font-family: 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
    padding: 50px;
    text-align: left;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-start;
  }
  footer {
    position: absolute !important; 
    top: 15px !important; 
    right: 30px !important; 
    left: auto !important; /* Assurez-vous que cette ligne est présente */
    font-size: 18px !important; 
    font-weight: 900 !important; 
    color: #58a6ff !important; 
    z-index: 1000; /* Ajoutez ce z-index pour vous assurer qu'il se superpose correctement */
  }
  h1 { color: #58a6ff; font-size: 1.1em; margin-bottom: 5px; }
  h2 { color: #58a6ff; font-size: 1.1em; margin-bottom: 5px; }
  .line { width: 100%; height: 2px; background: #58a6ff; margin: 8px 0 25px 0; }
  .lang-bar { font-size: 0.55em; color: #a5adba; margin-bottom: 20px; font-style: italic; }
  .intro-text { font-size: 0.8em; color: #ffffff; margin-top: 10px; font-weight: 300; }
  .item-group { margin-bottom: 25px; width: 100%; border-left: 4px solid #58a6ff; padding-left: 20px; }
  .item-main { 
    font-size: 0.85em; font-weight: bold; color: #ffffff; display: block; text-transform: uppercase;
   }
  .small-text {
    font-size: 0.6em; color: #a5adba; 
    vertical-align: middle;
  }
  .big-text {
    font-size: 1.5em; color: #58a6ff; 
    vertical-align: middle;
  }
  .item-sub { 
    font-size: 0.65em; color: #a5adba; display: block; margin-top: 5px;
  }
  .grid-9 {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-gap: 12px;
    width: 100%;
    height: 70%;
    align-self: center;
  }
  .grid-item {
    background: #161b22;
    padding: 10px;
    border-radius: 8px;
    border: 1px solid #30363d;
    text-align: center;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
  .grid-item strong { color: #58a6ff; font-size: 0.40em; text-transform: uppercase; }
  .grid-item span { font-size: 0.35em; color: #8b949e; margin-top: 4px; line-height: 1.2; }
  .no-wrap { white-space: nowrap; }
  .cloud-table { width: 100%; font-size: 0.4em; border-collapse: collapse; margin-top: 10px; }
  .cloud-table th { color: #58a6ff; text-align: left; padding: 10px; border-bottom: 1px solid #30363d; text-transform: uppercase; }
  .cloud-table td { padding: 10px; border-bottom: 1px solid #30363d; color: #a5adba; }
  .cloud-table b { color: #ffffff; }
  .translation-stack { margin-top: 3px; line-height: 1.2; }
  .small-lang { font-size: 0.8em; color: #a5adba; font-weight: normal; font-style: italic; display: block; }

---

![bg opacity:0.4 brightness:0.35](./../scenario_background.png)

# <span class="main-title">Enhancing Pipeline Efficiency : MTU and Jumbo Frames for Edge Network Optimization</span>
* **Focus**: Physical Transport Layer
* **Goal**: Eliminating the "Interrupt Storm"
* **Impact**: Optimizing the pipe before the code

---

<div class="grid-9">
  <div class="grid-item"><strong>DATA COLLECTION <br> (Source)</strong></div>
  <div class="grid-item"><strong>DATA INGESTION <br> (Pipeline)</strong><span>Jumbo Frames Optimized</span></div>
  <div class="grid-item"><strong>DATA PROCESSING <br> (Refining)</strong><span>Reduces overhead, optimizes bandwidth usage, and minimizes latency</span></div>
  <div class="grid-item"><strong>DATA QUALITY <br> (Validation)</strong><span></span></div>
  <div class="grid-item"><strong>DATA STORAGE <br> (Persistence)</strong><span></span></div>
  <div class="grid-item"><strong>DATA ANALYTICS <br> (Intelligence)</strong><span></span></div>
  <div class="grid-item"><strong>DATA TRANSFORMATION <br> (SYNTHESIS)</strong><span>Compressing and enriching data to high-value payloads</span></div>
  <div class="grid-item"><strong>DATA INTEGRATION <br> (Transport)</strong><span>Sending Jumbo Frames (MTU 9000) to the cloud</span></div>
  <div class="grid-item"><strong>DATA GOVERNANCE <br> (Lifecycle)</strong><span></span></div>
</div>

---

## Jumbo Frames (MTU 9000) are the "physical foundation" for 3 specific pillars
<div class="line"></div>

<table class="cloud-table">
  <tr>
    <th>Edge Function</th>
    <th>Description</th>
  </tr>
  <tr>
    <td><b>Ingestion<br>(Pipeline)</b></td>
    <td>Moving bits from sensors into local memory<br>without CPU "Interrupt Storms"</td>
  </tr>
  <tr>
    <td><b>Processing<br>(Refining)</b></td>
    <td>Freeing up to 30% of CPU cycles.<br>This "breathing room" is what actually enables local Refining</td>
  </tr>
  <tr>
    <td><b>Integration<br>(Transport)</b></td>
    <td>Aligning the Edge MTU with AWS/GCP backbones<br>for high-throughput, near real-time cloud delivery</td>
  </tr>
</table>

---

## Are you drowning in an "Interrupt Storm"?
<span class="item-sub">Standard network settings (1500-byte MTU) force high-volume Edge data into millions of tiny packets</span>

<div class="item-group">
  <span class="item-main">High-speed data streaming</span>
  <span class="item-sub">
  <b>CPU Overhead</b>: Every packet triggers an interrupt, forcing the CPU to stop tasks to process headers
  </span>
</div>

<div class="item-group">
  <span class="item-main">Handling raw binary signals</span>
  <span class="item-sub">
  <b>Resource Drain</b>: Up to <b>30%</b> of Edge Gateway CPU can be consumed just by network overhead
  </span>
</div>

<div class="item-group">
  <span class="item-main">Edge computing architecture</span>
  <span class="item-sub">
  <b>Energy Waste</b>: Millions of unnecessary packets lead to significant cumulative energy consumption
  </span>
</div>
<div class="line"></div>

---

## The Solution: Jumbo Frames (MTU 9000)
<span class="item-sub">By increasing the Maximum Transmission Unit (MTU) from 1500 to 9000 bytes, we fundamentally change the efficiency of data transport</span>

<div class="item-group">
  <span class="item-main">Packets Count Reduction <span class="small-text">(transfer 10 GB of data)</span></span>
  <span class="small-text">
  <!-- 1.2M (Jumbo) <b>vs</b> 7.3M (Standard) → <b>82% Reduction</b> -->
  Standard: 7.3M packets <b>vs</b> Jumbo: 1.2M packets → <b>82% of reduction</b>
  </span>
</div>

<div class="item-group">
  <span class="item-main">Overhead Cost Reduction <span class="small-text">(Min-Max)</span></span>
  <span class="small-text">
  Standard: 306MB – 394MB <b>vs</b> Jumbo: 51MB – 65MB → <b>NET SAVED: 255MB to 329MB</b>
  </span>
</div>

<div class="item-group">
  <span class="item-main">CPU Load Decrease</span>
  <span class="small-text">
  Smooth Flow <b>vs</b> Interrupt Storm →<b>High Saving</b><br>
  Reduced packet interrupts mean more deterministic CPU cycles<br>
  → <b>Reduction of electrical consumption and thermal dispersion</b><br>Especially in critical environments (e.g. Data Centers)
  </span>
</div>

---

## Critical Use Cases 🏭

<div class="item-group">
  <span class="item-main">Industrial Vision</span>
  <span class="item-sub">
  Streaming 4K/8K uncompressed video from GigE Vision cameras for automated quality control
  </span>
</div>

<div class="item-group">
  <span class="item-main">Medical Imaging</span>
  <span class="item-sub">
  Transferring large MRI, CT, and 3D scans (100s of MBs) with minimal latency for intra-operative procedures
  </span>
</div>

<div class="item-group">
  <span class="item-main">High-Frequency IoT</span>
  <span class="item-sub">
  Aggregating vibration analysis and telemetry from hundreds of sensors on a single Edge gateway
  </span>
</div>

<div class="item-group">
  <span class="item-main">Weather Simulation</span>
  <span class="item-sub">
  Ingesting massive real-time datasets (GBs/minute) from radar and satellite imagery
  </span>
</div>

---
## <span class="main-title">Pro-Tip: The End-to-End Chain ⛓️</span>
<span class="item-sub">
Jumbo Frames require <b>omogenous configuration</b>. A device not set for high MTU in the data path results in packet drops or fragmentation
<b>Critical Path to Verify</b>
</span>
<div class="line"></div>
<div class="item-sub">
<span class="big-text"><b>DATA SOURCE</b>:</span> Sensor, Camera, PLC<br>
<span class="big-text"><b>Network Switch</b>:</span> Must have Jumbo Frames enabled<br>
<span class="big-text"><b>Edge Gateway</b>:</span> Processing node NIC configuration<br>
</div>
<div class="line"></div>
<span class="small-text">
Note: This creates a "Data Highway" that aligns your Edge with the high-MTU backbones of AWS and Google Cloud
</span>

---

# Full-Stack Data Engineering 🚀

Optimizing at the Edge isn't just about elegant code. It's about mastering the entire stack—from the physical bit traversing the wire to the analytical query in the cloud<br><br>
> A robust network layer makes every subsequent optimization more effective
