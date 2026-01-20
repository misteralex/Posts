---
marp: false
theme: uncover
class: invert
paginate: true
footer: '@AF'
backgroundColor: #0d1117
style: |
  .main-title { font-size: 0.8em; color: #88b6ff; font-weight: 800; }
  .extra-title { font-size: 1.0em; color: #f53e48; font-weight: 800; }
  .extra-title::before { content: "☕"; margin-right: 0.25em; color: #800000; vertical-align: middle; }
  section { font-family: 'Segoe UI', Roboto, Helvetica, Arial, sans-serif; padding: 50px; text-align: left; display: flex; flex-direction: column; justify-content: center; align-items: flex-start; }
  footer { position: absolute !important; top: 15px !important; right: 30px !important; left: auto !important; font-size: 18px !important; font-weight: 900 !important; color: #58a6ff !important; z-index: 1000; }
  h1 { color: #58a6ff; font-size: 1.1em; margin-bottom: 5px; }
  h2 { color: #58a6ff; font-size: 1.1em; margin-bottom: 5px; }
  .line { width: 100%; height: 2px; background: #58a6ff; margin: 8px 0 25px 0; }
  .item-group { margin-bottom: 25px; width: 100%; border-left: 4px solid #58a6ff; padding-left: 20px; }
  .item-main { font-size: 0.85em; font-weight: bold; color: #ffffff; display: block; text-transform: uppercase; }
  .item-sub { font-size: 0.65em; color: #a5adba; display: block; margin-top: 5px; }
  .big-text { font-size: 1.5em; color: #58a6ff; vertical-align: middle; }
  .small-text { font-size: 0.6em; color: #a5adba; vertical-align: middle; }

---

![bg opacity:0.4 brightness:0.35](./../scenario_background.png)

# <span class="main-title">Enhancing Pipeline Efficiency : Payload & Deduplication</span>
* **Focus**: Application Layer  
* **Goal**: Lean & Unique Payloads  
* **Impact**: Faster ingestion, lower compute costs

---

## Lightening the Load: Local Refinement
<span class="item-sub">Don't waste bandwidth on noise—compress, aggregate, and serialize efficiently.</span>

<div class="item-group">
  <span class="item-main">Binary over Verbose</span>
  <span class="item-sub">Switch from heavy JSON to binary formats like <b>Protobuf</b> or <b>Avro</b></span>
</div>

<div class="item-group">
  <span class="item-main">Smart Compression</span>
  <span class="item-sub">Use <b>Zstd</b> or <b>Snappy</b> to compress data locally before sending</span>
</div>

<div class="item-group">
  <span class="item-main">Signal over Data</span>
  <span class="item-sub">Send refined aggregates or state changes instead of raw telemetry</span>
</div>

---

## Refining the Cargo: Deduplication Strategy
<span class="item-sub">Data duplication silently kills cloud performance. Ensure <b>idempotency at the source</b>.</span>

<div class="item-group">
  <span class="item-main">Beyond Timestamps</span>
  <span class="item-sub">Assign a unique <b>ULID</b> or <b>UUID</b> to every event at the Edge</span>
</div>

<div class="item-group">
  <span class="item-main">De-duping at Source</span>
  <span class="item-sub">Filter out redundant records before they ever hit the network</span>
</div>

---

## The <i>Data Engineering</i> Advantage: Making *UNION ALL* Fly
<span class="item-sub">Clean, unique data at the warehouse enables:</span>

<div class="item-group">
  <span class="item-main">Eliminate Expensive <b>UNION</b></span>
  <span class="item-sub">No more costly duplicate-removing operations</span>
</div>

<div class="item-group">
  <span class="item-main">Use <b>UNION ALL</b></span>
  <span class="item-sub">Lightning-fast ingestion without “double counting”</span>
</div>

<div class="item-group">
  <span class="item-main">Slash Compute Costs</span>
  <span class="item-sub">Reduce post-processing deduplication and associated CPU usage</span>
</div>

---

> <span class="item-sub"><i>Data Engineer</i> Insight: <br>
> A refined payload isn't just about saving bytes; 
it’s about <b>Data Integrity</b>. Lean & unique payloads at the Edge make every optimization downstream more effective</span>

---

## 💡 Data Engineer Insight: Reflect on Your Payload

<span class="item-sub">
<b>Is your payload really refined, or are you just moving bytes?</b>
Does it ensure <b>Data Integrity</b>?
Are your payloads at the Edge <b>lean and unique</b> enough to make downstream optimizations effective?<br><br>
</span>

<span class="item-sub">
Vos payloads à la périphérie sont-ils assez <b>légers et uniques</b> pour rendre efficaces les optimisations en aval ?<br><br>

Il tuo payload è davvero leggero e davvero ottimizzato per il <i>Cloud</i> ? Garantisce <b>l’integrità dei dati</b> ?
</span>
