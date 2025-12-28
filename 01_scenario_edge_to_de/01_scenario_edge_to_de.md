---
marp: true
theme: uncover
class: invert
paginate: true
footer: '@AF'
backgroundColor: #0d1117
style: |
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
    display: block !important;
    position: absolute !important;
    bottom: 30px !important;
    left: 50px !important;
    font-size: 27px !important;
    font-weight: 900 !important;
    color: #58a6ff !important;
  }
  h1 { color: #58a6ff; font-size: 1.6em; margin-bottom: 5px; }
  h2 { color: #58a6ff; font-size: 1.3em; margin-bottom: 5px; }
  .line { width: 100%; height: 2px; background: #58a6ff; margin: 15px 0 25px 0; }
  .lang-bar { font-size: 0.55em; color: #a5adba; margin-bottom: 20px; font-style: italic; }
  .intro-text { font-size: 0.8em; color: #ffffff; margin-top: 10px; font-weight: 300; }
  .item-group { margin-bottom: 25px; width: 100%; border-left: 4px solid #58a6ff; padding-left: 20px; }
  .item-main { font-size: 0.85em; font-weight: bold; color: #ffffff; display: block; text-transform: uppercase; }
  .item-sub { font-size: 0.65em; color: #a5adba; display: block; margin-top: 5px; }
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
  .grid-item strong { color: #58a6ff; font-size: 0.55em; text-transform: uppercase; }
  .grid-item span { font-size: 0.35em; color: #8b949e; margin-top: 4px; line-height: 1.2; }
  .no-wrap { white-space: nowrap; }
  .cloud-table { width: 100%; font-size: 0.6em; border-collapse: collapse; margin-top: 10px; }
  .cloud-table th { color: #58a6ff; text-align: left; padding: 10px; border-bottom: 1px solid #30363d; text-transform: uppercase; }
  .cloud-table td { padding: 10px; border-bottom: 1px solid #30363d; color: #a5adba; }
  .cloud-table b { color: #ffffff; }
  .translation-stack { margin-top: 5px; line-height: 1.2; }
  .small-lang { font-size: 0.8em; color: #a5adba; font-weight: normal; font-style: italic; display: block; }
---

![bg opacity:.4 brightness:.35](./01_scenario_background.png)

# From Edge to Refined Intelligence 
<div class="lang-bar">Connecting a device is no longer enough to call it 'smart'. The real challenge lies in real-time data refining: 
  operating on milliwatts while ensuring total privacy at the edge <br> <br>
  Des données orientées Cloud directement depuis les systèmes embarqués <br>
  Dati orientati al Cloud direttamente dai dispositivi integrati
</div>

From Raw Physical Signals to Cloud-Ready Insights <span style="font-size: 0.7em; color: #a5adba; font-style: italic;">
Physical Computing meets Cloud-Native Engineering <br> <br>

---

<div class="grid-9">
  <div class="grid-item"><strong>DATA COLLECTION <br> (Source)</strong><span>Capturing signals at the point of origin</span></div>
  <div class="grid-item"><strong>DATA INGESTION <br> (Pipeline)</strong><span>Moving raw bits into system memory</span></div>
  <div class="grid-item"><strong>DATA PROCESSING <br> (Refining)</strong><span>Transforming noisy waveforms into structured digital features</span></div>
  <div class="grid-item"><strong>DATA QUALITY <br> (Validation)</strong><span>Ensuring data integrity before it ever leaves the silicon</span></div>
  <div class="grid-item"><strong>DATA STORAGE <br> (Persistence)</strong><span>Efficient local persistence for fault-tolerant streaming</span></div>
  <div class="grid-item"><strong>DATA ANALYTICS <br> (Intelligence)</strong><span>Shifting analytical compute to the milliwatt level</span></div>
  <div class="grid-item"><strong>DATA TRANSFORMATION <br> (SYNTHESIS)</strong><span>Compressing complex signals into high-value smart payloads</span></div>
  <div class="grid-item"><strong>DATA INTEGRATION <br> (Transport)</strong><span>Seamlessly connecting Edge nodes to Cloud Data Lakes</span></div>
  <div class="grid-item"><strong>DATA GOVERNANCE <br> (Lifecycle)</strong><span>Managing the versioning and health of distributed intelligence</span></div>
</div>

---

## Cloud Integration Map
<div class="line"></div>

<table class="cloud-table">
  <tr>
    <th>Edge Function</th>
    <th>AWS Stack</th>
    <th>GCP Stack</th>
  </tr>
  <tr>
    <td><b>Ingestion</b></td>
    <td>IoT Core / Kinesis</td>
    <td>IoT Core / Pub-Sub</td>
  </tr>
  <tr>
    <td><b>Processing</b></td>
    <td>Lambda / Glue</td>
    <td>Cloud Functions / Dataflow</td>
  </tr>
  <tr>
    <td><b>Analytics</b></td>
    <td>Redshift/Timestream / S3</td>
    <td>BigQuery / Cloud Storage</td>
  </tr>
  <tr>
    <td><b>Governance</b></td>
    <td>IoT Device Management</td>
    <td>Fleet Management</td>
  </tr>
</table>

<div style="margin-top: 25px; font-size: 0.5em; color: #ffffff; font-weight: bold;">
Refining the Cloud pipeline at the Edge: Intelligence at the point of origin
</div>

---

## Sensori & Real-Time / Sensors
<div class="line"></div>

<div class="item-group">
  <span class="item-main">High-speed data streaming</span>
  <span class="item-sub">Deterministic <1ms Latency: The high-speed handshake for Cloud-native pipelines</span>
</div>

<div class="item-group">
  <span class="item-main">Handling raw binary signals</span>
  <span class="item-sub">On-device Data Validation | 99.9% Outlier Filtering</span>
</div>

<div class="item-group">
  <span class="item-main">Edge computing architecture</span>
  <span class="item-sub">Edge-Native Architecture | 90% Bandwidth Reduction via Local Synthesis</span>
</div>

---

## Data Efficiency & Payload Optimization
<div class="line"></div>

<div class="item-group">
  <span class="item-main">Downsampling Smart</span>
  <span class="item-sub">Reduce volume without losing entropy</span>
</div>

<div class="item-group">
  <span class="item-main">Local Aggregation</span>
  <span class="item-sub">From raw signals to high-level events</span>
</div>

---

## Hardware-Level Security & Data Privacy
<div class="line"></div>

<div class="item-group">
  <span class="item-main">Data Anonymization</span>
  <span class="item-sub">On-chip hashing & encryption</span>
</div>

<div class="item-group">
  <span class="item-main">Zero-Cloud Footprint</span>
  <span class="item-sub">Zero-Cloud exposure: Raw data stays on-chip, transmitting only refined insights</span>
</div>

---

## TinyML: On-Device Data Intelligence
<div class="line"></div>

<div class="item-group">
  <span class="item-main">Feature Engineering</span>
  <span class="item-sub">On-device feature extraction</span>
</div>

<div class="item-group">
  <span class="item-main">Anomaly Detection</span>
  <span class="item-sub">Pattern recognition on signals</span>
</div>

<div class="item-group">
  <span class="item-main">Quantization</span>
  <span class="item-sub">Compressing model weights without losing accuracy</span>
</div>

---

# Towards Intelligent Edge
<div class="lang-bar">To improve cloud data processes </div>

**Which point is critical for your project?** <br><br>
<span class="item-sub no-wrap"> 
Quel point est critique pour votre projet ? <br>
Quale di questi punti è critico per il tuo progetto ?
</span>
<style>
