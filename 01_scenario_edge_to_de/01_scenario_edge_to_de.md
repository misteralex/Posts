---
marp: true
theme: uncover
class: invert
paginate: true
footer: '@AF'
backgroundColor: #0d1117
style: |
  .main-title {
    font-size: 1.0em;
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
  .item-main { 
    font-size: 0.85em; font-weight: bold; color: #ffffff; display: block; text-transform: uppercase;
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

![bg opacity:0.4 brightness:0.35](./01_scenario_background.png)

# <span class="main-title">Smart Edge for Cloud-Ready Data</span>
<div class="lang-bar">
  Connecting a device is no longer enough to call it 'smart'. 
  The real challenge lies in real-time data refining: 
  operating on milliwatts while ensuring total privacy at the edge 
<br> <br>
  Des données orientées Cloud directement depuis les systèmes embarqués
  Dati orientati al Cloud direttamente dai dispositivi integrati
</div>

<span style="font-size: 0.5em; color: #a5adba; font-style: italic;">
Below are some critical challenges — and opportunities — where embedded systems 
design directly impacts the effectiveness of real-time data engineering at the edge
<br>
</span>

---

<div class="grid-9">
  <div class="grid-item"><strong>DATA COLLECTION <br> (Source)</strong><span>Capturing raw signals at the point of origin</span></div>
  <div class="grid-item"><strong>DATA INGESTION <br> (Pipeline)</strong><span>Efficiently moving bits into local memory</span></div>
  <div class="grid-item"><strong>DATA PROCESSING <br> (Refining)</strong><span>Transforming noisy waveforms into structured, meaningful features</span></div>
  <div class="grid-item"><strong>DATA QUALITY <br> (Validation)</strong><span>Ensuring integrity before any data leaves the device</span></div>
  <div class="grid-item"><strong>DATA STORAGE <br> (Persistence)</strong><span>Local buffering and temporary storage for fault-tolerant streaming</span></div>
  <div class="grid-item"><strong>DATA ANALYTICS <br> (Intelligence)</strong><span>Lightweight computation at the milliwatt level, near the sensor</span></div>
  <div class="grid-item"><strong>DATA TRANSFORMATION <br> (SYNTHESIS)</strong><span>Compressing and enriching data to high-value payloads</span></div>
  <div class="grid-item"><strong>DATA INTEGRATION <br> (Transport)</strong><span>Sending only refined, relevant data to the cloud</span></div>
  <div class="grid-item"><strong>DATA GOVERNANCE <br> (Lifecycle)</strong><span>Managing versions, metadata, and signal health on the edge</span></div>
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

## Sensors & Real-Time Data Processing
<div class="line"></div>

<div class="item-group">
  <span class="item-main">High-speed data streaming</span>
  <span class="item-sub">
  Low-latency data pipelines targeting deterministic sub-millisecond latency — an ideal design goal for real-time, 
  cloud-native processing at the edge
  </span>
</div>

<div class="item-group">
  <span class="item-main">Handling raw binary signals</span>
  <span class="item-sub">
  On-device data validation and filtering to remove noise and outliers before cloud ingestion
  </span>
</div>

<div class="item-group">
  <span class="item-main">Edge computing architecture</span>
  <span class="item-sub">
  Edge-native architectures enabling local synthesis and significant bandwidth reduction before data reaches the cloud
  </span>
</div>

---

## Data Efficiency & Payload Optimization
<div class="line"></div>

<div class="item-group">
  <span class="item-main">Smart downsampling</span>
  <span class="item-sub">
  Reducing data volume while preserving informational entropy
  </span>
</div>

<div class="item-group">
  <span class="item-main">Local Aggregation</span>
  <span class="item-sub">
  Transforming continuous raw signals into discrete, high-level events
  </span>
</div>

---

## Hardware-Level Security & Data Privacy
<div class="line"></div>

<div class="item-group">
  <span class="item-main">Data Anonymization</span>
  <span class="item-sub">
  On-chip hashing and encryption to enforce privacy by design
  </span>
</div>

<div class="item-group">
  <span class="item-main">Zero raw-data cloud exposure</span>
  <span class="item-sub">
  Raw signals remain on-device, with only refined and contextualized insights transmitted upstream
  </span>
</div>

---

## TinyML: On-Device Data Intelligence
<div class="line"></div>

<div class="item-group">
  <span class="item-main">Feature Engineering</span>
  <span class="item-sub">
  Extracting meaningful features directly on constrained devices
  </span>
</div>

<div class="item-group">
  <span class="item-main">Anomaly Detection</span>
  <span class="item-sub">
  Local pattern recognition to detect abnormal behavior in real time
  </span>
</div>

<div class="item-group">
  <span class="item-main">Quantization</span>
  <span class="item-sub">
  Reducing model size and compute requirements while preserving accuracy
  </span>
</div>

---

# Towards Intelligent Edge
<div class="lang-bar">
Improving cloud data processes starts with better data at the source
</div>

**Which of these challenges is most critical for your project?**

<span class="item-sub no-wrap"> 
Quel point est critique pour votre projet ? <br>
Quale di questi punti è critico per il tuo progetto ?
</span>
